# AutoClosing-SAMPLEALERT-FromMDfC
AutoClosing-SAMPLEALERT-FromMDfC

# How to use
This automation (Logics Apps) provides to close SAMPLE ALERTS from Microsoft Defender for Cloud.
Playbook will act the following sequences:

1. Detect [SAMPLE ALERTS] naming from Incident Title
2. Change to Severity as Informational.
3. Incident Close and reason as "Undetermined" and comments as "サンプルアラートのためクローズ"
4. Add Tag as "SAMPLE".

<img width="444" alt="image" src="https://user-images.githubusercontent.com/55295601/207754125-9254f119-5809-49de-a866-ce5356e53f25.png">

# Deploy to Azure
This button will provide deploys playbook. Let's enjoy!
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhisashin0728%2FAutoClosing-SAMPLEALERT-FromMDfC%2Fmain%2Fazuredeploy.json)
