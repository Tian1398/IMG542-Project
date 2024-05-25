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
