# Dataset Explanation and Tasks

This document outlines the structure of the provided datasets and the tasks to be performed as part of the capstone project. The goal is to evaluate data manipulation and analysis skills using Python libraries like NumPy and Pandas.

## Dataset Explanations

**Attributes:**

1.  **id:** A unique identifier assigned to the Project Head responsible for the project.
2.  **name:** The full name of the person handling the project.
3.  **gender:** The gender of the project head, denoted as 'Male(M)' or 'Female(F)'.
4.  **city:** The location where the project is based.
5.  **age:** The number of years the project is expected to be active.
6.  **status:** The current status of the project (e.g., Finished, Ongoing, Failed).
7.  **designation level:** The hierarchical position of the project head within the organization.
    * **Designation Scale:**
        * 1: Highest designation level
        * 2, 3: Mid-level positions
        * 4: Lowest designation level
        * **Rules:**
            * Excessive project failures may lead to a reduction in the designation level.
            * A strong positive track record increases the likelihood of a designation level promotion.
            * Any project head whose designation level exceeds 4 loses eligibility for heading projects.

## DataFrames

The project involves three distinct DataFrames:

### 1. Employee DataFrame

This DataFrame contains information about the employees heading the projects.

| ID   | Name        | Gender   | City       | Age |
| :----- | :---------- | :------- | :--------- | :-- |
| A001 | John Alter  | M        | Paris      | 25  |
| A002 | Alice       | F        | Luxumberg  | 27  |
| A003 | Tom Sabestine | M        | Berlin     | 29  |
| A004 | Nina Adgra  | F        | Newyork    | 31  |
| A005 | Amy Johny   | F        | Madrid     | 30  |

### 2. Seniority Level DataFrame

This DataFrame provides the initial designation level for each employee.

| ID   | Designation Level |
| :----- | :---------------- |
| A001 | 2                 |
| A002 | 2                 |
| A003 | 3                 |
| A004 | 2                 |
| A005 | 3                 |

### 3. Project DataFrame

This DataFrame contains details about each project handled by the employees.

| ID   | Project    | Cost      | Status   |
| :----- | :--------- | :-------- | :------- |
| A001 | Project 1  | 1002000   | Finished |
| A002 | Project 2  | 2000000   | Ongoing  |
| A003 | Project 3  | 4500000   | Finished |
| A004 | Project 4  | 5500000   | Ongoing  |
| A005 | Project 5  | NaN       | Finished |
| A002 | Project 6  | 680000    | Failed   |
| A005 | Project 7  | 400000    | Finished |
| A003 | Project 8  | 350000    | Failed   |
| A001 | Project 9  | NaN       | Ongoing  |
| A003 | Project 10 | 300000    | Finished |
| A001 | Project 11 | 2000000   | Failed   |
| A004 | Project 12 | 1000000   | Ongoing  |
| A004 | Project 13 | 3000000   | Finished |
| A005 | Project 14 | 200000    | Finished |

## Problems

**Task 1:**

Create three Pandas DataFrames in Python corresponding to the "Employee," "Seniority Level," and "Project" tables provided above. Save each of these DataFrames as a separate `.csv` file.

**Task 2:**

Load the "Project.csv" file. The "Cost" column contains missing values (NaN). Compute these missing values by calculating the running average of the "Cost" column. Implement this using a "For" loop. Replace the NaN values with the calculated running average.

**Task 3:**

Load the "Employee.csv" file. Split the "Name" column into two new columns: "First Name" and "Last Name". Remove the original "Name" column from the DataFrame.

**Task 4:**

Load the three `.csv` files created in Task 1. Join all three DataFrames into a single DataFrame. Name this resulting DataFrame "Final".

**Task 5:**

Add a new column named "Bonus" to the "Final" DataFrame. Assign a bonus of 5% of the "Cost" to employees whose project status is "Finished". For projects that are not "Finished", the bonus should be 0.

**Task 6:**

Load the "Final" DataFrame. For employees whose project "Status" is "Failed", demote their "Designation Level" by 1. After demotion, delete the records of any employees whose "Designation Level" is now greater than 4.

**Task 7:**

Load the "Final" DataFrame. Add the prefix "Mr." to the "First Name" of male employees and "Mrs." to the "First Name"
