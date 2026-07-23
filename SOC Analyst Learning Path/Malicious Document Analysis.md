## Introduction to Malicious Document File Analysis
- Macros used to deliver malware.
- Macros are small programs to automative repetitive (annoying) tasks in MS Office applications.
	- Typically written in VBA (Visual Basic for Applications).

## Static Malicious Document Analysis
- Static - study malware before execution.
1. `md5sum <document_name>`
2. `sha256 <document_name>
3. Copy the hashes to VirusTotal. Check scan results.
4. `exiftool <document_name>` - Shows metadata about file.
	- Take note of template key. If value includes `.dotm` it is a macro.
	- Comp-Obj-User-Type: `Microsoft Word 97-2003`
5. `strings -n 5 <document_name>` - Shows strings greater than length of 5.
	- Look for IP addresses, website, domains, file locations, malicious files, malicious code.
	- `autoopen` - Something would execute in background while running macros.
6. `xorsearch <document_name> <protocol i.e., http>` - Looks for encrypted strings and tries to decrypt them.
	- `xorsearch -p <document_name>` - Checks for embedded executables.

The questions below are based on the files included in the lab environment of this course lesson.
#### Q1: What is the MD5 value of the "/root/Desktop/QuestionFiles/PO-465514-180820.doc" file?
```
d7e6921bfd008f707ba52dee374ff3db
```
Run the `md5sum` command on the document.

#### Q2: What is the file type of the "/root/Desktop/QuestionFiles/PO-465514-180820.doc" file?
```
DOC
```
Run the `exiftool` command on the document.

## More Details About Document File Analysis 1
- `strings <document_name> | grep <i.e., https>` - Filters for a specific keyword.
1. `olemeta <document_name>` - Gives metadata of documents.
2. `oleid <document_name>` - Associates indicators with risk level.
	- Depending on file format, some commands may not work.
3. `olevba <document_name>`  - Searches for suspicious keywords related to VBA.

## More Details about Document File Analysis 2
- `olevba <document_name> > <output_file.vba>`
	- Right click the `output_file.vba` and open with Visual Studio Code.
- `olevba --deobf --reveal <output_file.vba> > <deobf_output_file.vba>`
	- Again open with Visual Studio Code.
	- Reveals decoded VBA strings (shown in a separate box).
- `vmonkey <output_file.vba>`
	- Ensure you get rid of the bottom part (where the box is), comments, anything not Visual Basic of the .vba file.
	- `vmonkey --iocs <output_file.vba>`
		- Shows indicators of compromise.
	- Look at Action, Parameters, Description.

The questions below refer to the files contained within the lab environment of this lesson.

**Note:** Before starting, install the oletools: "sudo -H pip install -U oletools"  
  
#### Q1: Does the file "/root/Desktop/QuestionFiles/PO-465514-180820.doc" contain a VBA macro?  
Answer Format: Y/N
```
Y
```
When running the command `olevba <document_name>`, the command outputs suspicious keywords related to VBA (i.e., Create, showwindow, CreateObject, ChrW).

#### Q2: Some malicious activity occurs when the document file "/root/Desktop/QuestionFiles/PO-465514-180820.doc" is opened. What is the macro keyword that enables this?
```
Document_open
```
This is one of the keywords found when answering the previous question.

#### Q3: Who is the author of the file "/root/Desktop/QuestionFiles/PO-465514-180820.doc"?
```
Alexandre Riviere
```
Can be found by using the `olemeta <document_name>' command.

#### Q4: What is the last saved time of the "/root/Desktop/QuestionFiles/PO-465514-180820.doc" file?
```
2020-08-18 08:19:00
```
Can be found by running command from previous question.

#### Q5: The malicious file "/root/Desktop/QuestionFiles/Siparis_17.xls" is trying to download files from an address. From which domain is it trying to download the file?
```
hocoso.mobi
```
Run `olevba Siparis_17.xls > Siparis.vba` then open the `Siparis.vba` in a text editor. Scroll all the way down until you see a box. In the box, the URL is listed.

#### Q6: How many IOCs are in the "/root/Desktop/QuestionFiles/Siparis_17.xls" file according to the Olevba tool?
```
2
```
Based on using the `olevba` command, only 2 IOCs were identified.

## Analysis with Sandboxes
- Any.Run, Hybrid Analysis
- CyberChef useful for decoding scripts (commonly base64).
	- From Base64
	- Remove null bytes (cleans up output)

The questions below refer to the files associated with the machine for this lesson.

**Note:** You can install Firefox on the Linux machine to upload the malicious file to Hybrid-Analysis or just use the hash search feature on Hybrid-Analysis.  
  
#### Q1: The file "/root/Desktop/QuestionFiles/PO-465514-180820.doc" is trying to make a request to a domain ending with ".kz". What is this domain?
```
www.msbc.kz
```

#### Q2: With which Windows tool are the connection requests made? (File: /root/Desktop/QuestionFiles/PO-465514-180820.doc)
```
powershell.exe
```

#### Q3: How many addresses does the file send DNS requests to? (File: /root/Desktop/QuestionFiles/PO-465514-180820.doc)
```
5
```

#### Q4: The "/root/Desktop/QuestionFiles/Siparis_17.xls" malware document is trying to download a file. With what name does he want to save the file it is trying to download to the device?
```
6LeGwKmrm.jar
```
