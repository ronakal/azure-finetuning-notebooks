Today, you'll explore how AI can transform financial document workflows by building an automated invoice processing solution that extracts, validates, and stores structured data from invoices. Through this hands-on lab, you will create an intelligent system capable of processing invoices in multiple formats, extracting key financial data, and generating actionable insights, powered by Azure AI Document Intelligence, Azure Blob Storage, and Power BI.

Scenario
Contoso Finance, a leading enterprise, processes hundreds of invoices daily from various vendors. Manual data entry from PDFs and scanned images causes frequent errors, delays payment processing, and creates bottlenecks during month-end closing. Quality analysts spend hours transcribing invoice numbers, vendor names, dates, line items, and totals, but high workload and inconsistent document formats lead to mistakes and lost early-payment discounts. To improve efficiency and accuracy, Contoso decides to build an Intelligent Document Processing solution that can automatically extract invoice data, validate it against business rules, and store results for reporting. This allows finance teams to process invoices instantly, make faster payment decisions, and maintain accurate audit trails across every transaction.
Deploy Azure AI Document Intelligence resources for invoice processing
Use the prebuilt invoice model in Document Intelligence Studio for automatic field extraction
Extract and review structured invoice data including vendor information and line items
Validate extracted data against financial business rules and accuracy requirements
Store processed invoice data in Azure Blob Storage containers
Create Power BI visualizations to analyze total spending, vendor distribution, and invoice trends

Challenge 01: Create Azure AI Document Intelligence Resource

In the Azure Portal, search for Document Intelligence and click Create.

Under Basics, provide:

Subscription: Use the available subscription.
Resource Group: Select challenge-rg-19974821997482.
Region: uksouthuksouth.
Name: finance-doc-intl-19974821997482.
Pricing Tier: Choose Free (F0).
Click Review + Create → Create.

Extract Data Using the Prebuilt Invoice Model
Steps to Complete
In the Azure Portal, open your Document Intelligence resource.

Challenge 02: Extract Data Using the Prebuilt Invoice Model
<img width="1466" height="613" alt="image" src="https://github.com/user-attachments/assets/ab771193-c768-4ce3-b4c5-178b8e184f3f" />

<img width="1464" height="683" alt="image" src="https://github.com/user-attachments/assets/c4e70e99-69f6-443c-b946-5a725f146f9d" />

<img width="1220" height="561" alt="image" src="https://github.com/user-attachments/assets/537093c4-78a7-44e1-8318-c2eb2930e884" />

Challenge 03: Validate Extracted Invoice Data

<img width="1750" height="755" alt="image" src="https://github.com/user-attachments/assets/18d3d9c3-d21a-4ffa-b00c-b742bcf7b86d" />
download the Json Files








