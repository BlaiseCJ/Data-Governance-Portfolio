# SME Governance Framework (Azure Purview)

**by BLAISE EZEOKEKE**

## **Overview**

This project demonstrates how I designed and implemented a **complete Data Governance Framework** for a small‑to‑medium enterprise (SME) environment using **Microsoft Purview**, **Azure Blob Storage**, and **Power BI**.

The goal was to show how data can be structured, classified, documented, and managed with clear ownership and compliance visibility in a modern cloud‑governed ecosystem.

![Collection .jpg](attachment:0b6c1385-5399-40b7-aa13-b9544ac2ad6d:Collection_.jpg)

## **Objective**

To build a scalable prototype governance architecture that:

- Automatically **catalogues and classifies** organisational datasets.
- Enables **PII identification**, data sensitivity labelling, and business glossary integration.
- Provides a transparent record of data ownership and stewardship.
- Generates metrics through **Data Estate Insights** and Power BI for audit and control.

## **Business Problem**

SME organisations frequently keep their data in disparate spreadsheets and storage locations without regulatory visibility.

This results in multiple versions of the same information, increased compliance risk, and unclear responsibility for data quality.

The project solved this by introducing a **central governance hub** with automation, built‑in classification, and contextual metadata management.

---

## **Technology Stack**

| Layer | Tools / Services |
| --- | --- |
| **Data Source** | Azure Blob Storage (Container: datasets) |
| **Governance Platform** | Microsoft Purview Studio |
| **Integration Runtime** | Azure AutoResolveIntegrationRuntime |
| **Visualization / Reporting** | Purview Data Estate Insights |
| **Supporting Docs** | Word & GitHub Portfolio |

---

## **Step‑by‑Step Implementation**

### **1. Provisioning and Setup**

- Created a new **Azure Purview Account** named *SME‑Governance‑Demo* with supporting resource group and region (UK South).
- Registered the **Microsoft.Storage** resource provider to enable linking between Purview and Blob Storage.
- Created the storage account *purviewblobdemo265* and a container *datasets* for data uploads.

![SME Governance Azure Purview.jpg](attachment:7e3b006c-59fb-4c0a-a3f1-9ad7c19c26c8:SME_Governance_Azure_Purview.jpg)

### **2.  Dataset Creation and Upload**

- Generated dummy employee records in CSV (*sme_employees.csv* ) containing `EmployeeID, Full Name, Department, Email, Start Date, Role`.
- Uploaded the files to the Azure Blob Storage container.

![Registering Azure Blob Data Source.jpg](attachment:bca166d8-c706-4275-a626-53836e5921fe:Registering_Azure_Blob_Data_Source.jpg)

### **3.  Data Source Registration and Scanning**

- Registered Azure Blob Storage as a Purview data source under the *SME‑Governance‑Demo* collection.
- Ran initial scans (Level 2 and Full Rule Set) using Purview’s managed identity with **Storage Blob Data Reader** permissions.
- Verified successful cataloguing and schema discovery through `Data Catalog → Assets → sme_employees.csv`.

### **4.  Classification Implementation**

- Applied system‑generated and manual classifications
    - *Full Name* → PII tag
    - *Email Address* → Sensitive information
    - *Department* → Internal data
- Created additional custom classifications for “Confidential Data” and “Internal Use Only.”

### **5.  Business Glossary Development**

- Created glossary term **Employee Record** under SME‑Governance‑Demo collection.
- Steward/Expert: Blaise Ezeokeke.
- Category: HR Data.
- Synonyms: Staff Record, Personnel File, HR Dataset.
- Related terms: Department, Payroll Record, Confidential Data.
- Linked this term directly to `sme_employees.csv` asset through Purview’s resource‑association feature.

![Glossary.jpg](attachment:68a037ed-823f-4d0d-81b2-24a42d0a21cf:Glossary.jpg)

### **6. Data Ownership and Stewardship**

- Assigned **Blaise Ezeokeke** as both *Data Steward* and *Expert* for all catalogued datasets.
- Established metadata attributes such as *Data Sensitivity Level = Confidential*  and *Source System = HR Database.*

### **7.  Insights and Compliance Dashboard**

- Enabled **Data Estate Insights** in Purview Studio to compute governance metrics. Assets scanned: 4 (Blob files)

       Assets classified: 2 (with PII tags)

       PII types detected: Email Address, Full Name

- Created complementary **Power BI dashboard** ( GovernanceDashboard.pbix ) to display KPIs for compliance coverage and classification trends.

![Data Estate Insights.jpg](attachment:ef8d5a3f-ab07-4b8c-a5f7-f70fe8d12660:Data_Estate_Insights.jpg)

### **8.  Portfolio Documentation**

- Compiled completed screenshots:

Purview Studio landing page (“SME Governance Demo”)

Data map with Azure Blob source Classifications and Glossary term view Data Estate Insights overview

- Saved project artefacts to GitHub repository *Data‑Governance‑Portfolio‑Blaise.*

---

## **Results**

| Metric | Outcome |
| --- | --- |
| Data assets catalogued | 1 ( `sme_employees.csv` ) |
| Fields classified | Full Name + Email Address PII tags |
| Glossary terms linked | Employee Record → Confidential Data → Department |
| Steward assigned | Blaise Ezeokeke |
| Dashboard created | Data Estate Insights + Power BI Governance Report |
| Compliance readiness | 95 % coverage for HR dataset PII classification |

---

## **Key Deliverables**

1. End‑to‑end governance framework deployed in Azure Purview.

2. Business Glossary built and connected to catalogued data.

3. Classifications applied for PII, Internal, and Confidential information.

4. Stewardship and ownership aligned to governance best practice.

5. Insight dashboard presenting measurable compliance KPI metrics.

---

## **Skills Demonstrated**

- Azure Purview administration & configuration.
- Data classification and PII detection using Purview rule sets.
- Metadata management and business glossary design.
- Data stewardship and ownership alignment.
- Power BI compliance dashboard creation.
- Documentation and portfolio presentation.

---

## **Conclusion**

This project successfully established a **modern data governance blueprint** showing how SMEs can:

- Centralise data assets;
- Apply quality and compliance controls;
- Define clear ownership; and
- Maintain transparency using Azure Purview.

Through this framework, I achieved measurable governance outcomes — metadata cataloguing, PII identification, and a functional insight dashboard — all of which demonstrate enterprise‑grade governance capability within a single Microsoft ecosystem.