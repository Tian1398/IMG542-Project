# PROJECT INTRODUCTION & INSTRUCTION

The Use, Audience & Impact

This project aims to streamline the extraction and processing of data from communication tools (Gmail) (Microsoft Teams), converting it into a format suitable for network analysis on the Polinode software. By automating this process, it can help users better understand human interactions from their communication data. The primary use of this pipeline is to facilitate the analysis of communication patterns and organizational dynamics within a network of relationships. The target audience includes data analysts, individual business owners, or anyone who is interested in understanding and enhancing communication workflows and efficiency. Access to the data will be restricted to people who have valid Gmail or Teams accounts and are authorized to access it. Notably, this project attempts to improve utilizing communication data for network analysis from an individual user’s perspective rather than from an organizational perspective.

User Access

The code for data extraction and data transformation will be published on this GitHub repository. The access will be free and open for the public. After obtaining the original data and metadata from the communication tool (gmail), users are welcomed to review, copy, and edit the example coding files in this repository and run the code individually in their local environment. If successful, users will expect to be able to download the transformed data in their desired format (excel), so it is ready for Polinode ONA analysis.

Methodology

To generate the information structure and maintain it, this project consist of mainly 2 sections: 

1) Data Extraction
Use Google Takeout page to access the user’s account and export email data. The information structure is in mbox formats, with inbox and sent data stored separately in distinct files.
or
Use the Export page with the user’s Microsoft Account to access and download Teams data. Please note that work or school accounts are not supported via this method.

2) Data Transformation
Perform validation steps to ensure basic data requirements are met before feeding the original data to the transformation.
Write Python code to load, clean, manipulate, and output data according to Polinode's standards.
Include documentation to improve process transparency and make it easier for troubleshooting.

Instruction to Use the Code Example in this repository

- Please ensure that you have accessed and obtained your gmail data first and have your Inbox and Sent box mbox data ready.
- Ensure basic data requirements are met before feeding the original data to next steps.
- Iterate through each message in the Inbox & Sent mbox files, extract key info.
- Combine Inbox and Sent box datasets.
- Expand multi recipient edges (to address the cases where one person sends a message to multiple recipients).
- Calculate frequency.
- Clean names to remove email addresses → edges
- Create a separate data frame with unique email names → nodes
- Save 2 data frames into one file.

Limitations

1. This application might not be able to properly address all data contents from the original datafiles. It needs a more robust data cleaning pipeline to address more complicated and diversified data.

2. It needs a more nuanced approach on different forms of communication such as cc / bcc / conversations and assigning them different weights, so that the visualization results would demonstrate more insights.

3. This application needs a more user-friendly interface, so that the user could transform their data by clicking their mouse rather than running the program.


# IMG542-Project Test Plan

The goal of this test plan is to ensure that the pipeline for accessing and transforming data from Microsoft Teams is reliable and able to respond under various conditions. I hope to use regular monitoring, testing, and maintenance to support the system's ongoing success.

Desired outcomes:
1. With correct credentials, the pipeline can accurately access data from Microsoft Teams.
2. The data is manipulated correctly while maintaining original values.
3. Users can download the transformed data in their desired formats (JSON or Excel).
4. Report issues or errors promptly.

To ensure these desired outcomes to be implemented on an ongoing basis, I mainly rely on the functional tests, checking that each individual function works well.

1. API Access Test
Expected Result: Data is successfully retrieved from the Microsoft API without errors.
Method: I will test the application with various user credentials and permissions.

2. Data Transformation Test
Expected Result: Transformed data matches the expected format and retains original values.
Method: I will check the output data file’s data format, and then compare input JSON data with transformed data.

3. Data Download Test
Expected Result: Users can download data in the specified format, and the data is accurate.
Method: I will explicitly look into the downloaded file, checking its format (both JSON and Excel), and opening the file to ensure it contains the right content.
the download functionality for formats.

4. Error Report Test
Expected Result: Prompt notifications for any issues requiring immediate attention.
Method: I will create alarms for key metrics such as API response failures or essential data elements missing for transformation. Also, I will test with various sample users to understand the potential errors. I want to include a feature that auto notifies the system and reports the error type, but I decided to not include it due to both workload and privacy concerns.

In addition, I hope to include performance testing, making sure that functions still perform when lots of load comes in. For example, I hope that my application can still perform as a large data file with a more complex data structure dome in. To do so, I will use a Teams account with a large volume of data and measure the relevant performance metrics such as processing time and resource usage (CPU/GPU)
