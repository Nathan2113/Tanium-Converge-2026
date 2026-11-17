### Vulnerability Response Workflow
![](assets/Pasted%20image%2020261116153607.png)



### Setup

1. Open the Service Graph Connector for Tanium

- Service Graph Connectors > Tanium > Setup

![217](assets/Pasted%20image%2020261116153711.png)

- On the page header, change the app scope to "Service Graph Connector for Tanium"

![311](assets/Pasted%20image%2020261116153805.png)



2. Walk the SGC guided setup wizard

- Click on `Review` in the "Getting Started" form

![](assets/Pasted%20image%2020261116153837.png)

- Click on `Set Authentication Type` and select `Configure` to view the configuration values

![](assets/Pasted%20image%2020261116153928.png)

- Go back to `Configure the Connection and Credentials` overview and select `Configure` next to `Configure the Token auth Credentials` to view connection's Host Name and MID Server options

![](assets/Pasted%20image%2020261116154113.png)

- Select `Configure` next to `Configure the View`

![](assets/Pasted%20image%2020261116154204.png)

- Note the selected view, typically named "ServiceNow SGC"

![](assets/Pasted%20image%2020261116154241.png)

- Select `Configure` next to `Configure the Scheduled Import`

![](assets/Pasted%20image%2020261116154311.png)

- Select `SG-Tannium Hardware and Software` and review the configured schedule

![](assets/Pasted%20image%2020261116154338.png)

- Go to `TAB Executions` to see the Data imports

![](assets/Pasted%20image%2020261116154403.png)


3. Review the reconciliation history

- Open the most recent concurrent import set for the `SG-Tanium Hardware and Software` data source
	- Select System Import Sets > Advanced > Concurrent Import Sets

![285](assets/Pasted%20image%2020261116154458.png)

- Open the most recent import set for `SG-Tanium Hardware and Software`
	- can sort the `Number` column to find easily

![](assets/Pasted%20image%2020261116154522.png)

- Open the `Import Set Runs` and confirm the state of the most recent is is "Processed"

![](assets/Pasted%20image%2020261116154606.png)

- Open one of the records (blue number) `Import Set Rows` tab and note number of inserts and updates

![](assets/Pasted%20image%2020261116154638.png)


4. Explore a live Computer CI record

- Open the `Computers` list and identify records populated by the connector
	- Configuration > Windows

![255](assets/Pasted%20image%2020261116154717.png)

- If the `Discovery Source` column isn't available, use `Personalize List` to add it

![](assets/Pasted%20image%2020261116154750.png)

![240](assets/Pasted%20image%2020261116154804.png)

- Open one `SG-Tanium` sourced Windows CI and review its OS version, patch status, and `Updated` timestamp


5. Validate freshness and debrief

- Open the `Integration Dashboard` to get an overview of how the Tanium Service Graph is running and performing

![299](assets/Pasted%20image%2020261116154932.png)

- filter by connectors if necessary

![](assets/Pasted%20image%2020261116155005.png)





### Real-time Vulnerability Identification; Mapping CVE's to Exposed Endpoints (CI's)

1. Open the Security Exposure Management Workspace and review active exposure

- Go to `Exposure Management Workspace`

![278](assets/Pasted%20image%2020261116155306.png)

- Review dashboard summarizing active findings across the env

![](assets/Pasted%20image%2020261116155331.png)


2. Filter by CVE to isolate exposed endpoints

- In the `Security Management Workspace`, change the dashboard to `Exploitable`

![314](assets/Pasted%20image%2020261116155404.png)

- Go to widget `Findings by Vulnerability`

![445](assets/Pasted%20image%2020261116155427.png)

- Choose a machine, can see when it was last updated and compliance

![434](assets/Pasted%20image%2020261116155506.png)

![453](assets/Pasted%20image%2020261116155515.png)

- Verify a finding is from Tanium by clicking on a vulnerability > Select an active finding > verify source
	- can get more info about a CVE by clicking into it in the findings

![325](assets/Pasted%20image%2020261116155731.png)


3. Confirm data freshness and cross-reference findings

- Review endpoint details within `Security Exposure Management Workspace` > click Tanium in `Findings by Source` > open finding (can also filter if needed) > go to `Affected Configuration Item` > review `Vulnerable Items`, `Preferred Solutions`, and `Preferred Patches` by clicking the numbers on the widgets

![335](assets/Pasted%20image%2020261116160212.png)

![433](assets/Pasted%20image%2020261116160222.png)

![221](assets/Pasted%20image%2020261116160235.png)

![596](assets/Pasted%20image%2020261116160247.png)

![436](assets/Pasted%20image%2020261116160257.png)

![](assets/Pasted%20image%2020261116160308.png)


4. Use Watch Topic for ongoing monitoring

- Go to `Exposure Management` and click on `Watch Topics`

![505](assets/Pasted%20image%2020261116160338.png)

- Click on `Tanium Discovered Vulnerabilities (Critical/High)`

![](assets/Pasted%20image%2020261116160406.png)

- To see CVE related CI's, go to `Impacted CI's`

![](assets/Pasted%20image%2020261116160429.png)


5. Review the Remediation Effort

- From the `Watch Topic` dashborad, go bac to `Tab Overview` and click on a remediation record

![527](assets/Pasted%20image%2020261116160500.png)

- All needed data to manage the remediation is present, such as risk rating, risk score, etc

![547](assets/Pasted%20image%2020261116160544.png)

- Verify that the Remediation Tasks are assigned to the appropriate team

![533](assets/Pasted%20image%2020261116160616.png)

![518](assets/Pasted%20image%2020261116160628.png)


6. Confirm patch applicability and debrief

- Use Tanium patch info to confirm the correct patch/KB package maps to the target CVE

- Open Remediation task VUL0010006 

![541](assets/Pasted%20image%2020261116161541.png)

- Go to widget `Preferred Patches` and click on the number in the widget

![521](assets/Pasted%20image%2020261116161611.png)

- See an overview of all preferred patches related to the CI and related CVE's

![](assets/Pasted%20image%2020261116161647.png)


