---
name: 'De-Integration for Cognos controller'
about: De-Integration for Cognos controller  Git Issue
title: 'De-Integration for Environment-- xxx - Client Name: <Customer Name>'
labels: SRE1-ChangeMgmt,SRE2-Provisioning,SRE-XS-Hours
assignees: suddiitm
---


| Salesforce Case              | []                                      |
| ---------------------------- | --------------------------------------------- |
| 🔻 Downtime Needed                                        | 4 hours                       |
| **Customer**                 |         |
| **Environment - Prod**       |         |
| **Data Center**              |         |
| **CA Environment** |  |
| **PA Environment**|   |
| **Downtime**                         | `YYY-MM-DD HH:MM-HH:MM UTC`  |
| **PA De-Integration**| |
| **JIRA Issue**|   |



---

## Case Description

❗ Do not copy paste customer email, Contact number from case details

---


**Steps:**
- [ ] Set up GOBOT maintenance Alert N/A (@gobot ba maintenance)
- [ ] Run `powershell .\controller_decouple_pa_configure_standalone.ps1 -ccConfigFilePath <ccCfgFilePath> -paConfigFilePath <paCfgFilePath>`
- [ ] [Validation](https://github.ibm.com/BA-CloudOps/BA-Ops-Documentation/blob/master/Controller/03.Runbooks/Provisioning/Validation.md)
  - [ ] [Validation script](https://github.ibm.com/BA-CloudOps/BA-Ops-Documentation/blob/master/Controller/03.Runbooks/Provisioning/Validation.md#validate-script)
  - [ ] [SFTP validation](https://github.ibm.com/BA-CloudOps/BA-Ops-Documentation/blob/master/Controller/03.Runbooks/Provisioning/Validation.md#confirm-you-are-able-to-connect-to-sftp)
  - [ ] Able to launch website `https://<clusterName>.controller.ibmcloud.com` and navigate to login.ibm.com (:warning: Only the ADM can login successfully)
  - [ ] Verify IBMId email of the ADM
    - Open `Sql Server Management Studio` (ssms.exe) in jumpbox
    - Connect to data tier (`<clusterName>dacc`) using `Windows Authentication`
    - Invoke `SELECT * FROM ccr01.dbo.xibmiduser` (check for ccr01, ccr02, ccr03 and ccr04)
    - Verify the ADM is same as the IBMId email 
- [ ] [Welcome kit](https://github.ibm.com/BA-CloudOps/BA-Ops-Documentation/blob/master/Controller/03.Runbooks/Provisioning/Sending_Welcome_kit.MD#generate-the-welcome-kit) (Updated to use script)
- [ ] update SF ticket
