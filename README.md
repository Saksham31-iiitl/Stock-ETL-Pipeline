**API LINK**: https://www.alphavantage.co/

#### **Technologies and Tools**

- **Python** for data extraction, transformation, and CSV generation (using `requests` and `pandas`).
- **AWS S3** for data storage.
- **Boto3** library for programmatically interacting with AWS S3.


### **Steps to Complete the Project**
---

#### **Step 1: Set Up Your Environment**
Ensure you have the following Python libraries installed:

- `requests` for API calls to retrieve data.
- `pandas` for handling and transforming data.
- `boto3` for loading data into AWS S3.


#### **Step 2: Extract Data from the API**
We’ll connect to a stock time series API to fetch the latest stock data for analysis.

- **API Request**: Use `requests` to retrieve JSON data from the API.
- **Data Extraction**: Focus on the `Time Series (5min)` portion of the JSON, which contains time-stamped data about stock prices.

#### **Step 3: Data Exploration and Cleaning**
Explore the JSON data to confirm that it has the fields needed, and prepare it for transformation.

#### **Step 4: Data Transformation**
To streamline the dataset, we’ll keep only essential fields: timestamp, open, high, low, close, and volume.

- **Filter Data**: Extract only the needed columns from each time-stamped entry.
- **Transform to DataFrame**: Convert the filtered data into a `pandas` DataFrame for easy manipulation.

#### **Step 5: Save Data to CSV**
Instead of saving the data directly to disk, we use an in-memory buffer with `StringIO` to hold the CSV file contents. This approach is efficient for uploading data directly to cloud storage, such as AWS S3, without creating an intermediate file.

#### **Step 6: Load Data into AWS S3**
We’ll use the `boto3` library to upload the CSV file to an S3 bucket.

1. **Initialize S3 Client**: Set up a connection to AWS S3.
2. **Upload the CSV**: Programmatically upload the CSV file to the specified S3 bucket.

