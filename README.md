# practical11

Aim: Create dataset and load dataset

Theory:

pd.DataFrame(data) This converts a raw Python dictionary into a structured, two-dimensional table. It aligns the keys as column headers and the lists as the rows of data.

df.to_csv("filename.csv", index=False) This exports the current DataFrame into a physical CSV file. The index=False part is crucial because it prevents pandas from adding an extra, unnamed column for the row numbers into your file.

pd.read_csv('path/to/file.csv') The primary way to pull external data into Python. It reads the file and reconstructs it into a DataFrame so you can start manipulating it.

df.info() This is the technical "X-ray" of the dataset. It shows the total number of entries, the data type of each column (like int64 for numbers or object for text), and tells you exactly how many non-null values exist.

df.head() and df.tail() These are your quick-look tools. head() grabs the first five rows and tail() grabs the last five. It's the fastest way to verify that your data loaded correctly and isn't corrupted at the start or end.

df.sample(n) Unlike the head or tail, this picks n random rows from anywhere in the dataset. This is used to spot-check data for consistency without being biased by how the file is sorted.

df.columns This returns a simple list of all the column headers in the DataFrame. It’s useful when you need to copy-paste exact column names for filtering or calculations.

df.describe() The statistical powerhouse. It automatically calculates the count, mean, standard deviation, minimum, maximum, and quartiles (25%, 50%, 75%) for every numerical column. It ignores text columns and focuses strictly on the math.

df.isnull().sum() This is a data-cleaning essential. isnull() identifies every empty cell (NaN), and .sum() adds them up per column so you know exactly where your data is missing.

df.duplicated().sum() This scans the entire DataFrame for rows that are 100% identical. It returns a single number representing how many "trash" or repeat rows need to be deleted.

df.nunique() This counts how many distinct, unique values are in each column. For example, if you have 93 cars but only 32 manufacturers, this command will highlight that categorical relationship.

Conclusion:

The experiment demonstrates the complete data lifecycle: creation, storage, and structural auditing. By using pd.DataFrame and to_csv, data is transitioned from memory to persistent storage. Subsequent analysis via info(), describe(), and isnull() ensures the dataset is high-quality by identifying missing values and distribution patterns. This systematic approach transforms raw data into a reliable foundation for informed decision-making.
