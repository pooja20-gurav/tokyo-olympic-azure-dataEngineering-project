# Tokyo-Olympic-azure-Data_Engineering-project


## Description

This project takes data about the Tokyo Olympics from a CSV file on GitHub and puts it into the Azure system using a tool called Azure Data Factory. The data is first stored in a place called Azure Data Lake Storage Gen2. Then, some changes and improvements are made to the data using another tool called Azure Databricks. The improved data is put back into Azure Data Lake Storage Gen2.
After that, the data goes through more advanced analysis in Azure Synapse, another tool in the Azure ecosystem. The final results and insights from the data can be seen either in Azure Synapse or in a visualization tool like Power BI. This whole process gives us a thorough and clear understanding of the Tokyo Olympic dataset.

## Architecture

![Architecture](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/d79c73d2-8d82-48c7-b15f-99f074f1cc07)



## Dataset:

The dataset utilized encompasses information on more than 11,000 athletes engaged in 47 disciplines, involving 743 teams in the 2021 (2020) Tokyo Olympics. It provides comprehensive details about the athletes, coaches, participating teams, and gender-specific entries. The dataset includes information such as names of athletes, countries they represent, the discipline they participate in, the gender of competitors, and the names of their coaches.



## Azure Services Used

- Azure Data Factory: Used for ingesting data from GitHub.
- Azure Data Lake Storage Gen2: Served as the primary storage solution for the data.
- Azure Databricks: Utilized for carrying out data transformation processes.
- Azure Synapse Analytics: Employed for conducting comprehensive data analytics.


# Workflow

1. Azure Free Subscription Account Creation:

- Begin by setting up an Azure Free Subscription account to access Azure services.

2. Resource Group Creation:
- Establish a Resource Group named 'tokyo-olympic-data' to serve as the centralized entity for managing all Azure resources linked to this project.

3. Storage Account Setup:

- Within the 'tokyo-olympic-data' resource group, create a storage account tailored to harness the capabilities of Azure Data Lake Storage (ADLS) Gen2.

4. Container Creation:

- Inside the newly established storage account, set up a container to house the project's data. This container is specifically configured to leverage ADLS Gen2 capabilities.

5. Directory Structure:

- Within the created container, organize the data into two distinct directories:
   - 'raw-data': Dedicated to storing the raw, unprocessed data.
   - 'transformed-data': Reserved for storing data that has undergone transformation processes.
 
  
![Storage_Group](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/ed6cb377-2548-46e1-9e8e-c92458884776)



# Data Ingestion using Azure Data Factory

1. Create Azure Data Factory Workspace:

- Within the established resource group, initiate the creation of an Azure Data Factory workspace.

2. Launch Azure Data Factory Studio:

- Access the Azure Data Factory Studio interface after successfully setting up the workspace.

3. Upload Tokyo Olympics Dataset to GitHub:

- Obtain the Tokyo Olympics dataset from Kaggle and upload it to your GitHub repository.

4. Initialize Data Integration Pipeline:

- Within the studio, create a new data integration pipeline as the foundation for managing data movements.

5. Use Copy Data Task:

- Employ the "Copy Data" task within the pipeline to facilitate the efficient transfer of data between different sources and destinations.

6. Configure Data Source with HTTP Template:

- Set up the data source, utilizing the HTTP template to make requests to the GitHub repository for data retrieval.

7.Establish Linked Service for Source:

- Create a Linked Service to establish the connection with the data source, ensuring seamless interaction with the HTTP template.

8. Configure File Format:

- Define the file format for the data being transferred and set up the Linked Service Sink to manage the destination.

9. Repeat for Each Dataset:

- Duplicate the aforementioned steps for each dataset in the project to ensure all relevant data is loaded.

10.Connect Copy Data Activities:

- Link all the "Copy Data" activities together within the pipeline to create a cohesive flow, allowing for the simultaneous execution of data transfer processes.


By following these subpoints, you systematically create, configure, and manage the flow of data from GitHub to Azure Data Factory for your Tokyo Olympics dataset.


 ![Data_pipeline](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/adee5482-06b1-48a9-9338-17a1ef9a75eb)

11. After the pipeline completes its execution, navigate to your Azure Data Lake Storage Gen2. Dive into the "raw_data" folder and validate that the files, like "athletes.csv", "medals.csv", etc., are present and populated with the expected data.

![Raw_data](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/c6b35d49-3190-4b3a-b990-91142ed2bcc3)

# Data Transformation using Azure Databricks

1. Go to Azure Databricks:
- Open the Azure portal and find Azure Databricks in the group of resources you made earlier. Click to open the Databricks workspace.

2. Set Up Databricks:
- Arrange the computing power you need in Databricks for transforming your data.


3.Create a New Notebook:
- Make a new notebook inside Databricks and give it a name that says what it's for, like "Data Transformation.

4. Connect to Data Storage (ADLS):
- Get some special codes (Client ID, Tenant ID, Secret) and use them in the notebook to connect Databricks to where your data is stored, like Azure Data Lake Storage (ADLS).

5. Write Transformation Code:
- In the notebook, write code to change and improve your data. This code will use the connected ADLS as a starting point.

6. Connect ADLS to Databricks:
- Use the special codes again to connect ADLS to Databricks so that it's easy to get the data you want.

7.Save Transformed Data:
- After making your data better, save it back to ADLS. This way, your improved data is stored and ready to use.

![Transformed_daa](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/bd580ce3-9113-48f7-bf2e-940634d3e659)

# Analyzing the Dataset: Uncovering Insights from the Data


![azure_synapse](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/e17a9b0b-aa54-45ec-8da1-91c24f5fd76c)

- Write a SQL script to Explore Data: Use SQL to check out the data and create reports with PowerBI if needed.

  can refer this link : https://raw.githubusercontent.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/main/SQL%20script%202.sql


![SQL script 2](https://github.com/pooja20-gurav/tokyo-olympic-azure-dataEngineering-project/assets/81917801/38b6b12d-d381-4ae3-87de-d92820228501)







