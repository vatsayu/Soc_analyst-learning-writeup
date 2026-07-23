## File Analysis with VirusTotal

There are detection tags about how the file is classified. See below image:
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/VirusTotal+for+SOC+Analysts/images/image-3.png"/>

It is important to take a look at the First Submission and Last Submission field as the results may vary from time to time.

### Relations
- This tab shows info about domain, IP, URL, and other files.
- Can use this check suspicious communication activities.
- A detection score indicates reputation.
- Should be aware the list is not comprehensive.

### Behavior
- This tab shows activities such as network connections, DNS queries, file reading/deletion, registry actions, and process activities.
- You can specify by manufacturer (1) for the results.
<img src="https://ld-images-2.s3.us-east-2.amazonaws.com/VirusTotal+for+SOC+Analysts/images/image-8.png"/>

#### Q1: According to the analysis report in the link, what is the creation date of the file?  
[https://www.virustotal.com/gui/file/415ba65e21e8de9196462b10dd17ab81d75b3e315759ecced5ea8f5812000c1b/details](https://www.virustotal.com/gui/file/415ba65e21e8de9196462b10dd17ab81d75b3e315759ecced5ea8f5812000c1b/details)  
  
Answer Format: YYYY-MM-DD
```
2020-08-20
```

#### Q2: According to the VirusTotal result, how many URL addresses does the malicious file communicate with? You must enter number.  
[https://www.virustotal.com/gui/file/415ba65e21e8de9196462b10dd17ab81d75b3e315759ecced5ea8f5812000c1b/relations](https://www.virustotal.com/gui/file/415ba65e21e8de9196462b10dd17ab81d75b3e315759ecced5ea8f5812000c1b/relations)
```
14
```

#### Q3: Examine the analysis report, what is the '**Compilation Timestamp**' of the file? (You should copy paste the timestamp from VT.)  
[https://www.virustotal.com/gui/file/6c745b8c701574b32cce2cdec63de7e669127cc0aa6afa654165ebd46c4252b4/detection](https://www.virustotal.com/gui/file/6c745b8c701574b32cce2cdec63de7e669127cc0aa6afa654165ebd46c4252b4/detection)
```
2022-07-17 22:57:46 UTC
```

## Scanning URLs with VirusTotal
#### Q1: In which category is google.com classified according to Sophos?    
[https://www.virustotal.com/gui/url/cf4b367e49bf0b22041c6f065f4aa19f3cfe39c8d5abc0617343d1a66c6a26f5/detection](https://www.virustotal.com/gui/url/cf4b367e49bf0b22041c6f065f4aa19f3cfe39c8d5abc0617343d1a66c6a26f5/detection)

```
search engines
```
Can be found in the Details section.

#### Q2: In which category is letsdefend.io classified according to Forcepoint ThreatSeeker?  
[https://www.virustotal.com/gui/domain/letsdefend.io/details](https://www.virustotal.com/gui/domain/letsdefend.io/details)

```
information technology
```
Had to use `https://letsdefend.io` instead of `letsdefend.io` to find this answer as the Categories section was not showing in the VirusTotal scan result.

#### Q3: What is the name of the hash file "**349d13ca99ab03869548d75b99e5a1d0**" scanned in VirusTotal?
```
1word.doc
```

## Searching for IOC
Using the **Search** section on VirusTotal, you can view past VirusTotal results, files, IPs, and URL associations.

#### Q1: Search VirusTotal for the MD5 value “**b92021ca10aed3046fc3be5ac1c2a094**”. What is the First Submission date? (YYYY-MM-DD)
```
2019-09-16
```

## Key Points to Pay Attention
- Should pay attention to when was the last time the VirusTotal scan occurred.
	- Attackers typically generate a harmless URL and scan it in VirusTotal.
	- Then they replace content of URL with something harmful.
	- Recommended to reanalyze.
- Check the detection tags - may not necessarily mean file is harmful.
