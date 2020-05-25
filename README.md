# Data Engineer
## DP-200
 - Reference: https://github.com/MicrosoftLearning/DP-200JA-Implementing-an-Azure-Data-Solution
   - Following the https://github.com/MicrosoftLearning/DP-200JA-Implementing-an-Azure-Data-Solution/tree/master/Instructions files in order.
   - dp-200-01_instructions.md: 
   - dp-200-02_instructions.md: Create Storage Account, Storage Account(with Hierarchy/ADLS option)
   - dp-200-03_instructions.md: Create Databricks Workspace & DBC(like ipynb) files and read json file data from Storage Account(with Hierarchy/ADLS option)
     - App Registration(DLAccess) and Databricks Access via **DLAccess** Auth(`DLAccess Application(Client) ID`, `DLAccess Directory(Tenant) ID`, `DL Access key(authentication-id)`) → **Resource Group IAM**(`Role assignments` to DLAccess) → **Storage Account(with Hierarchy/ADLS option)** → Container