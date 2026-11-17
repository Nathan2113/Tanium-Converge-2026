**App Remediation Workflow**
1. Anomalous Software (Atlas) > Filter by risk level (high or critical)

![](assets/Pasted%20image%2020261116103708.png)

2. ask Atlas what the criticality of the app is (e.g. Wireshark)
3. Correlate app to findings in Comply
4. Uninstall risky app with Deploy
5. Block app from returning with Applocker Enforcement policy





**Investigate CVE Batch in Comply**
1. Copy Glasswing CVE feed from browser into Atlas > ask Atlas to filter by Vendor = Microsoft and Product = Windows

![](assets/Pasted%20image%2020261116104153.png)

2. Ask Atlas which of those CVEs are present in your environment

![](assets/Pasted%20image%2020261116104205.png)

4. Ask Atlas for the EPSS score and CVSS v3 severity of each Glasswing CVE affecting your endpoints, whether any of them appear in the CISA Known Exploited Vulnerabilities (KEV) catalog, and whether any known botnets or ransomware operations are associated with them.

![](assets/Pasted%20image%2020261116104252.png)

5. Ask Atlas if a patch exists for the CVEs, and the confidence score if they do 

![](assets/Pasted%20image%2020261116104445.png)

6. Patch team decides next steps

*Note: You can create an ADC (Automated Deployment Configuration) - It turns the approved criteria, targets, and deployment plan into a standing rule for future matching patches.*
- *Future matching patches are deployed automatically without creating and approving a new manual deployment each time*




**Discover and Close an External Surface Exposure**
1. Open Atlas and use the Attack Surface Overview template

![](assets/Pasted%20image%2020261116105033.png)

2. Filter down to hosts with critical findings

![](assets/Pasted%20image%2020261116105127.png)

3. Select a host to get more info

![](assets/Pasted%20image%2020261116105146.png)

4. Go to web properties with critical findings

![](assets/Pasted%20image%2020261116105232.png)

5. Select view discovery path to see how an asset was discovered

![](assets/Pasted%20image%2020261116105321.png)

6. Can also view self-signed certificates (and expiry dates) and replace them with Atlas

![](assets/Pasted%20image%2020261116105434.png)
![](assets/Pasted%20image%2020261116105442.png)
![](assets/Pasted%20image%2020261116105453.png)
![](assets/Pasted%20image%2020261116105504.png)





**Identify and Remediate Attack Paths - Crown Jewels**
1. Atlas > Command Palette > Attack Paths

![](assets/Pasted%20image%2020261116105634.png)

2. Add columns to prioritize attack paths

3. Filter down by specific attack path

![](assets/Pasted%20image%2020261116105756.png)

4. Click `View Path Details` to get step by step path

![](assets/Pasted%20image%2020261116105854.png)

5. Click nodes to get justification for why they're considered a crown jewel or choke point

![](assets/Pasted%20image%2020261116110009.png)
![](assets/Pasted%20image%2020261116110024.png)

- choke point if it says "Closes x open paths if remediated"

6. On a choke point, click `View Blast Radius` to see how many crown jewels are reached from that node

![](assets/Pasted%20image%2020261116110145.png)


7. Confirm the choke point is on the KEV

![](assets/Pasted%20image%2020261116110228.png)


8. Ask Atlas if there's any patch available

9. Ask Atlas to create an ADC > Review configuration and deploy

