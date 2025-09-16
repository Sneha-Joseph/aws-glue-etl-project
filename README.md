# ETL Pipeline using AWS Glue and S3

## Project Overview
This project demonstrates an ETL (Extract, Transform, Load) pipeline using **AWS Glue** and **Amazon S3**. The pipeline reads data from two source files stored in S3, performs a join operation, filters unnecessary columns, and writes the final output back to another S3 bucket.

---

## 📂 Input Files

The following two datasets are stored in Amazon S3 as CSV files:

1. **AmazonS3emp** (`emp_1.csv`): Employee data including columns like Employee ID, Name, Department ID, Location, Email, etc.
2. **AmazonS3dept** (`department.csv`): Department data including Department ID, Department Name, etc.

---

## 🔄 ETL Pipeline Steps

### 1. **Data Sources**
- Two S3 buckets are configured as data sources.
- `emp_1.csv` contains employee details.
- `department.csv` contains department details.

### 2. **Join Transformation**
- The datasets are joined based on a common key (e.g., `Department ID`).
- This helps in merging relevant data from both datasets for further analysis.

### 3. **Drop Fields Transformation**
- After joining, irrelevant columns like `Location` and `Email` are removed.
- This ensures that only necessary information is processed and stored.

### 4. **Data Target**
- The final transformed dataset is uploaded to an output S3 bucket (`AmazonS3output`).
- The data is stored in CSV format for easy access and further processing.

---

## 🛠 Technologies Used
- **Amazon S3**: For storing input and output files.
- **AWS Glue**: For performing the ETL operations including joins and field filtering.
- **CSV format**: For data interchange between the buckets.

---

## 🚀 How to Use

1. Upload `emp_1.csv` and `department.csv` to separate S3 buckets.
2. Set up an AWS Glue job:
   - Define the two data sources pointing to the S3 buckets.
   - Apply a Join transformation on the common field.
   - Use the Drop Fields transformation to remove unwanted columns.
   - Define the target S3 bucket for the output data.
3. Run the Glue job.
4. Verify the output file in the target bucket.

---

## 📂 Files in this Repository
- `emp_1.csv`: Employee dataset.
- `department.csv`: Department dataset.
- `README.md`: Documentation for setting up and running the project.

---

## 📌 Notes
- This project is designed for demonstration purposes and can be extended to include additional transformations.
- Ensure proper IAM roles and permissions are configured for S3 and Glue.

