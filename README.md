# AutoClosing-SAMPLEALERT-FromMDfC
AutoClosing-SAMPLEALERT-FromMDfC

This automation (Logics Apps) provides to close SAMPLE ALERTS from Microsoft Defender for Cloud.
Playbook will act the following sequences:

1. Detect [SAMPLE ALERTS] naming from Incident Title
2. Change to Severity as Informational.
3. Incident Close and reason as "Undetermined" and comments as "サンプルアラートのためクローズ"
4. Add Tag as "SAMPLE".

<img width="444" alt="image" src="https://user-images.githubusercontent.com/55295601/207754125-9254f119-5809-49de-a866-ce5356e53f25.png">

# Deploy to Azure
Here is a instruction to install Automation template for Sentinel.
## 1. Install Template
This button will provide deploys playbook.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhisashin0728%2FAutoClosing-SAMPLEALERT-FromMDfC%2Fmain%2Fazuredeploy.json)

## 2. Require AAD Rule for Logic Apps
This template create Logic Apps that is used authentication by Managed ID.
The workflow requires 'Microsoft.SecurityInsights/incidents/read' to the target Microsoft Sentinel, so please assign suitable role for managed id.
![image](https://user-images.githubusercontent.com/55295601/207772809-3f784ed0-7780-4099-ab6b-c28a3c4752dc.png)
Here is a sample 
<img width="964" alt="image" src="https://user-images.githubusercontent.com/55295601/207773171-d6f493cc-0c16-41a3-8b8f-ad9664c00223.png">


