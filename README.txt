How to add Block County IP's in Windows Firewall with PowerShell.

Step 1: Create a directory for working with PowerShell and PowerShell Scripts. Example - C:\ip-security

Step 2: Download the PowerShell script Import-Firewall-Blocklist.ps1 from http://www.gregsitservices.com/ip-security/ip-security-package.zip and extract the PowerShell script Import-Firewall-Blocklist.ps1 to your C:\ip-security folder. *If you're reading this file you most likely already obtain this package*

Step 3: Go to this website and download the IP Tables of the countries that you do not want accessing your windows system at all. To the Right of each list grab the "aggregated zone file" for each country. Click them on them and you will see a list of IP's. Right click and save that file to your C:\ip-security directory using a basic format, THIS IS IMPORTANNT. Example, save china as china.zone.txt so that if you update the zone file it will remove any Old Rules that are created. Optionally you can grab the larger lists (on the left) but, the aggregated zones are based on activity. 

I recommend the following Zones:
 1) CHINA (CN) (save as china.zone.txt)
 2) KOREA, DEMOCRATIC PEOPLE'S REPUBLIC OF (KP) (save as northkorea.zone.txt)
 3) KOREA, REPUBLIC OF (KR) (save as southkorea.zone.txt)
 4) RUSSIAN FEDERATION (RU) (save as russia.zone.txt)

Step4: Run PowerShell and Administrator (right click PowerShell and select Run As Administrator).

Step 5: Type without quotes "PowerShell.exe -ExecutionPolicy Bypass" - This will set the scripts Policy of PowerShell to run so that it can make the Windows FireWall Rules.

Step 6: Begin entering the Zones into your Windows FireWall. Option 1 is for Older Versions of PowerShell. If Option 1 does not execute then use Option 2.

 Option 1: Import-Firewall-Blocklist.ps1 -inputfile china.zone.txt

 Option 2: .\Import-Firewall-Blocklist.ps1 -inputfile china.zone.txt

Do this for each of your Zones.

Step 7: Just for precaution let's now set PowerShell back to Restricted Access on Scripts. Type without quotes "PowerShell.exe -ExecutionPolicy Restricted".

That's it we are done... I suggest you keep your zone files so that you can update them easy by overwriting them. I would update them about Once a Month if you are experiencing attacks. Below is how you can remove the entries using the scripts and zone files.

 Option 1: Import-Firewall-Blocklist.ps1 -inputfile china.zone.txt -deleteonly

 Option 2: .\Import-Firewall-Blocklist.ps1 -inputfile china.zone.txt -deleteonly


ENJOY!


Best regards,

Greg (TRI0N) Munson
