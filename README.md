# Live Jobs Aggregator — End-to-End Data Engineering Pipeline

## 📌 Project Overview

The **Live Jobs Aggregator End-to-End Data Engineering Pipeline** is a project built using Databricks that collects job listings from Google Jobs through the SerpApi API, processes the data using the Bronze, Silver, and Gold layers of the Medallion Architecture, and generates visualizations to analyze job market trends.

The project uses **Databricks notebooks and a scheduled pipeline** to orchestrate the complete workflow. Instead of manually executing each notebook, the pipeline runs the three processing layers in sequence on a recurring schedule. In this implementation, the pipeline is configured to execute every **5 minutes**, allowing repeated job data collection and processing while the schedule remains enabled.

The final Gold-layer data supports bar plot visualizations of top companies by job postings and job demand across cities.

## 🎯 Project Objectives

- Extract job listings from Google Jobs using SerpApi.
- Retrieve API data using the appropriate URL and query parameters.
- Implement a multi-layer data pipeline using the Medallion Architecture.
- Process data through Bronze, Silver, and Gold layers.
- Orchestrate multiple Databricks notebooks in a single pipeline.
- Schedule recurring pipeline executions at 5-minute intervals.
- Visualize job market trends using company-wise and city-wise job posting counts.

## 🏗️ Pipeline Architecture

<img width="1392" height="632" alt="Google Jobs Aggregator End-to-End Pipeline Architecture(2)" src="https://github.com/user-attachments/assets/c79d8549-4d5f-4a82-a836-fc27f7e65a67" />


## ⚙️ Technologies Used

- **Databricks** — Notebook development and pipeline orchestration.
- **SerpApi** — API integration to retrieve Google Jobs search results.
- **Google Jobs API** — Source of job listing information through SerpApi.
- **Bronze Layer** — Storage of fetched job data in its raw form.
- **Silver Layer** — Processing and refinement of job data.
- **Gold Layer** — Preparation of data for analytical queries and visualization.
- **Data Visualization** — Bar plots for analyzing company-wise job postings and city-wise job demand.

*Add your exact programming language, processing framework, storage technology, and visualization library to this section if applicable.*

## 🔄 Data Pipeline Workflow

### 1. Data Extraction — SerpApi
- Connected to SerpApi to retrieve job listings from Google Jobs.
- Used the API URL and query parameters to request job search results.
- Fetched job-related information for downstream processing.

### 2. Bronze Layer — Raw Data Ingestion
- Retrieved job listing data from the API.
- Stored the extracted data in the Bronze layer.
- Maintained the initial data layer for subsequent processing.

### 3. Silver Layer — Data Processing
- Read data from the Bronze layer.
- Processed and refined job listing records.
- Prepared the data for analytical transformations.

### 4. Gold Layer — Analytics-Ready Data
- Read the processed data from the Silver layer.
- Prepared the final dataset for job market analysis.
- Used the Gold-layer data as the source for visualizations.

### 5. Databricks Pipeline Orchestration
Created a Databricks pipeline/workflow to coordinate the three notebook tasks instead of running each notebook manually.
**Key features:**
- **Automated execution:** Runs the Bronze, Silver, and Gold notebooks as part of one orchestrated workflow.
- **Scheduled runs:** Configured a recurring execution interval of 5 minutes.
- **Sequential processing:** Executes the layers in the required order so downstream processing can use upstream data.
- **Repeated data ingestion:** Repeats the workflow while the schedule remains enabled, allowing the dataset to be refreshed with newly retrieved job listings.

The 5-minute interval represents the configured workflow schedule, not a guarantee that each complete pipeline run finishes within 5 minutes. Actual execution time depends on API response times, data volume, and compute availability.

### 6. Data Visualization
Created bar plots using the processed job listing data.
- **Top Companies by Job Postings:** Compares the number of job listings associated with different companies.
- **Job Demand by Cities:** Compares job posting counts across cities to understand the geographic distribution of advertised opportunities.

## 📊 Visualizations

### Top Companies by Job Postings

Displays companies ranked by the number of job postings found in the collected dataset.

### Job Demand by Cities

Displays the distribution of job postings across cities, helping identify locations with more advertised opportunities.

The visualizations reflect the collected dataset and can change as new data is ingested.

## ⚙️ Pipeline Scheduling

The Databricks workflow is configured to run automatically every **5 minutes**.

| Configuration | Details |
|---|---|
| Orchestration platform | Databricks |
| Processing tasks | Bronze, Silver, Gold notebooks |
| Execution mode | Scheduled workflow |
| Configured interval | Every 5 minutes |
| Manual execution | Not required for each scheduled cycle |
| Continuous operation | Repeats while the schedule is enabled and the workflow is active |

The workflow automates the execution of the notebooks. It does not guarantee that Google Jobs listings change during every cycle, and the pipeline's actual refresh behavior depends on the API response and the data processing logic.

### 💡 Key Learning Outcomes
- Integrating external APIs into a data engineering pipeline.
- Implementing the Bronze, Silver, and Gold layers of the Medallion Architecture.
- Developing modular data processing notebooks in Databricks.
- Orchestrating notebook dependencies through a scheduled workflow.
- Automating recurring data ingestion and transformation.
- Preparing analytical datasets for downstream visualization.
- Analyzing job market trends using company-wise and city-wise aggregations.

### 🔐 API Key and Configuration
This project requires a SerpApi API key.
1. Create an account on SerpApi.
2. Obtain an API key from your SerpApi dashboard.
3. Store the API key securely using Databricks secrets or environment variables.
4. Configure the required API parameters in your notebook.
5. Set up the Databricks workflow and configure its schedule.

**Security:** Never upload API keys, access tokens, or other credentials to GitHub.

## 🚀 Future Improvements
- Implement incremental data processing to reduce unnecessary reprocessing.
- Add duplicate detection for job listings.
- Track changes in job postings over time.
- Add data quality checks and pipeline failure notifications.
- Analyze job listings by skills, experience level, and employment type.
- Develop an interactive dashboard for job market analytics.
- Optimize API usage and scheduled execution frequency.

## 👨‍💻 Author

**Jay Falak**

- GitHub: https://github.com/Jay-2468
- LinkedIn: https://www.linkedin.com/in/jay-falak-b511a0212/

---

⭐ If you find this project interesting, feel free to explore the repository and share your feedback.
