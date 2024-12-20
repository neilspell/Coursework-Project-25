# Data Analysis with Pandas 🐼
In this lesson, we’ll explore **data analysis** using a dataset of student grades. 

The measures we’ll look at include:

1. Viewing and Exploring the Data
2. Selecting Specific Columns and Rows
3. Adding New Columns
4. Sorting Data
5. Calculating Averages

We will work with a **DataFrame**, which is like a table of data. Each example uses a dataset created below:

````py
# Creating our dataset
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie", "David", "Eve"],
    "Age": [16, 17, 16, 18, 17],
    "Grade": ["B", "A", "C", "A", "B"],
    "Math_Score": [78, 88, 65, 90, 82],
    "Science_Score": [85, 92, 70, 95, 89],
}

# Convert the data into a pandas DataFrame
df = pd.DataFrame(data)
print(df)
````

👉 Run the code above in `Thonny` to create the DataFrame.

---

## 1. Viewing and Exploring the Data 👨‍💻
Before analyzing data, we need to understand its structure. 

👉 Try the following in `Thonny` to inspect the dataset:

````py
# Display the first few rows of the dataset
print("First few rows:")
print(df.head())

# Display summary information about the dataset
print("\nDataset Info:")
print(df.info())

# Display basic statistics about numerical columns
print("\nBasic Statistics:")
print(df.describe())
````

💡 **Note:** _`head()` gives you a quick preview of the data, and `describe()` summarizes the numerical data._

---

## 2. Selecting Columns and Rows 🔎
We often need specific parts of the data for analysis. Here’s how to **select a column**:

````py
# Select the "Math_Score" column
print("Math Scores:")
print(df["Math_Score"])
````

👉 Run the code to extract the Math scores.

### Selecting Multiple Columns
What if you want more than one column? Use the following code:

````py
# Select "Name" and "Grade" columns
print("\nName and Grade Columns:")
print(df[["Name", "Grade"]])
````

👉 Try running this and observe how it returns a smaller table.

---

## 3. Adding New Columns 🆕
We can calculate new information from the data. Let’s compute a **Total Score** for each student by adding their Math and Science scores.

````py
# Add a "Total_Score" column
df["Total_Score"] = df["Math_Score"] + df["Science_Score"]
print("\nData with Total Score:")
print(df)
````

💡**Note:** _Notice how Pandas allows easy addition of new columns._

---

## 4. Sorting Data 🔀
Sorting helps identify patterns or rank data. Let’s sort the students by their **Total Score**:

````py
# Sort by Total_Score in descending order
sorted_df = df.sort_values(by="Total_Score", ascending=False)
print("\nSorted by Total Score:")
print(sorted_df)
````

👉 Run the code to find out which student has the highest total score!

---

## 5. Calculating Averages 🧮
We can calculate the **average score** for Math to get an overall idea of how the class performed:

````py
# Calculate the average Math score
avg_math_score = df["Math_Score"].mean()
print(f"\nAverage Math Score: {avg_math_score}")
````

💡**Note:**  _We can use `.mean()` to find averages for numerical columns easily._

---

## Extra Credit ✨
1. Add a column called `Percentage_Score` that shows the percentage of total marks (out of 200).
2. Find the average of `Science_Score` for the class.
3. Filter the data to display only students with a `Grade` of "A".
4. Save the updated DataFrame to a new file using `.to_csv()`.
