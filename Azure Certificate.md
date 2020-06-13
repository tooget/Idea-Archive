# [Data Engineer Associate](https://docs.microsoft.com/ko-kr/learn/certifications/azure-data-engineer)
 - [X] [DP-200](https://docs.microsoft.com/ko-kr/learn/certifications/exams/dp-200) / 2020-06-11, 14:15~, online
 - [X] [DP-201](https://docs.microsoft.com/ko-kr/learn/certifications/exams/dp-201) / 2020-06-13, 15:00~, 渋谷 / ~2022-06-13
## DP-200 : https://github.com/MicrosoftLearning/DP-200JA-Implementing-an-Azure-Data-Solution, https://tsfb.learnondemand.net/
 - Following the https://github.com/MicrosoftLearning/DP-200JA-Implementing-an-Azure-Data-Solution/tree/master/Instructions files in order.
 - dp-200-01_instructions.md: 
 - dp-200-02_instructions.md: Create Storage Account, Storage Account(with Hierarchy/ADLS option)
 - dp-200-03_instructions.md: Create Databricks Workspace & DBC(like ipynb) files and read json file data from Storage Account(with Hierarchy/ADLS option)
     - App Registration(DLAccess) and Databricks Access via **DLAccess** Auth(`DLAccess Application(Client) ID`, `DLAccess Directory(Tenant) ID`, `DL Access key(authentication-id)`) → **Resource Group IAM**(`Role assignments` to DLAccess) → **Storage Account(with Hierarchy/ADLS option)** → Container
     - Another tutorials:     https://github.com/MicrosoftDocs/mslearn-perform-basic-data-transformation-in-azure-databricks/blob/master/DBC/05.1-Basic-ETL.dbc?raw=true
 - dp-200-04_instructions.md: Create Cosmos DB(SQL(DocumentBased)) & SQL-like Query
 - dp-200-05_instructions.md: Create Synapse Analytics & Query & Load Data from Storage Account(ALDS) using PolyBase
```sql
CREATE EXTERNAL DATA SOURCE AzureStorage
WITH (
    TYPE = HADOOP,
    LOCATION = 'abfs://data@awdlsstudxx.dfs.core.windows.net',
    CREDENTIAL = AzureStorageCredential
);
```
 - dp-200-06_instructions.md: Create Event Hubs, Stream Analytics & SQL-like Query on Stream Data Window
   - Input should be json and have keys to be queried.
   - Use PolyBase to save results.
```sql
SELECT System.Timestamp AS WindowEnd, COUNT(*) AS FraudulentCalls
INTO "PhoneCallRefData"
FROM "PhoneStream" CS1 TIMESTAMP BY CallRecTime
JOIN "PhoneStream" CS2 TIMESTAMP BY CallRecTime
ON CS1.CallingIMSI = CS2.CallingIMSI
AND DATEDIFF(ss, CS1, CS2) BETWEEN 1 AND 5
WHERE CS1.SwitchNum != CS2.SwitchNum
GROUP BY TumblingWindow(Duration(second, 1))
```
 - dp-200-07_instructions.md: Create DataFactory & Run ETL Pipeline to insert results in Synapse Analytics201
 ## DP-201 : https://github.com/MicrosoftLearning/DP-201JA-Designing-an-Azure-Data-Solution


# [Solutions Architect Expert](https://docs.microsoft.com/ko-kr/learn/certifications/azure-solutions-architect)
 - [ ] [AZ-300](https://docs.microsoft.com/ko-kr/learn/certifications/exams/az-300) / 2020-06-15, 13:15~, online
 - [ ] [AZ-301](https://docs.microsoft.com/ko-kr/learn/certifications/exams/az-301)

# [Database Administrator Associate](https://docs.microsoft.com/ko-kr/learn/certifications/azure-database-administrator-associate)
 - [ ] [DP-300](https://docs.microsoft.com/ko-kr/learn/certifications/exams/dp-300) / 2020-06-22, 13:00~, online

# [Developer Associate](https://docs.microsoft.com/ko-kr/learn/certifications/azure-developer)
 - [ ] [AZ-204](https://docs.microsoft.com/ko-kr/learn/certifications/exams/az-204) / 2020-06-19, 13:00~, online

# [AI Engineer Associate](https://docs.microsoft.com/ko-kr/learn/certifications/azure-ai-engineer)
 - [X] [AI-100](https://docs.microsoft.com/ko-kr/learn/certifications/exams/ai-100) / 2020-06-04, 14:00~, online / ~2022-06-04

# [Data Scientist Associate](https://docs.microsoft.com/ko-kr/learn/certifications/azure-data-scientist)
 - [ ] [DP-100](https://docs.microsoft.com/ko-kr/learn/certifications/exams/dp-100)
## DP-100 : https://github.com/MicrosoftLearning/DP-100JA-Designing-and-Implementing-a-Data-Science-Solution, https://github.com/MicrosoftLearning/DP100 

# [Data Fundamentals](https://docs.microsoft.com/ko-kr/learn/certifications/azure-data-fundamentals)
 - [ ] [DP-900](https://docs.microsoft.com/ko-kr/learn/certifications/exams/dp-900)

# [AI Fundamentals](https://docs.microsoft.com/ko-kr/learn/certifications/azure-ai-fundamentals)
 - [ ] [AI-900](https://docs.microsoft.com/ko-kr/learn/certifications/exams/ai-900)

# [Fundamentals](https://docs.microsoft.com/ko-kr/learn/certifications/azure-fundamentals)
 - [X] [AZ-900](https://docs.microsoft.com/ko-kr/learn/certifications/exams/az-900) / 2020-02-08