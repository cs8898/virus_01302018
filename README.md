# WARNING MALWARE CONTAINS ORIGINAL CODE SNIPPETS
## virus01302018

Symptom:
========
The Virus symptom was the automated mute of the microphone, after setting the microphone volume to 100% it alwase dropped some seconds later back to 0%.  

Detection:
==========
I was pretty sure the had to be some kind of malicious software so i installed MalwareBytes
MalwareBytes managed to detect suspicious web traffig wich gave me information about the running process

Logic:
======
The Software wars inited from the shell:startup folder, the script launched was reading the code from the registry (first layer) [trojan.js]  
Now a JavaScript is going to be evaluated, with some string encryption (second layer) [Z9vqXquhwwBW8.js]  
After running this code you will get the value in [Z9vqXquhwwBW8value.js] wich will launch a PowerShell running another script wich is given as argument (third layer)  
The Powershell script seems like generating another layer of code, but at this point i stopped digging [trojan.ps1]  

Remarks:
========
Some files are missing also files with cryptic names where found in %LocalAppData% there were some .exe files wich re spawned after deletion.  
It seemed that the Virus had differen entry points, not only the shell:startup one...  
I was able to remove the files by booting a liveCD after deletion i cleaned the registry in the path i was given from the script from autorun (this is the code containing in this repo).  

