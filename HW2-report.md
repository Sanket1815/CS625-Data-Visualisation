# HW 2 - CS 625, Spring 2024

**Sanket Nadkarni**

Due: January 31, 2024

## Part 1 - Data Cleaning

- Loaded the DataSet into OpenRefine.
- Remove row/columns:-

  - Removed all blank rows/columns by running command :-
  - `if(isBlank(cells['Job Title'].value), 'remove', if(cells['Job Title'].value == '-1', 'remove', value))`

- Editing the values in the column:-
  To get the highest value for column size:-

  - `if(isBlank(value), "0", value.split(" ")[-2])`.
  - This will get us the last value which will be the highest.
    ![Highest value](/assests/images/HighestValue.png)

- Creating a new column:-

  - In location column dropdown, I selected Add column based on this column option. So a new column will be created with values same as location column and I named it State. Then I used this command to extract state name from location :-
  - `value.split(",")[1].trim()` as the data is stored in "City, State" format.
  - Then rename the location column as City. And for extracting only city name used this command :- `value.split(",")[0].trim()`.

- Creating Relability Column:-
  - Below is the code for each criteria on rating column:-
  - `if(value == null, "Unknown", if(value <= 2, "OK", if(value <= 2.5, "Good", if(value <= 3.5, "Very Good", "Excellent"))))`
    ![Reliability](/assests/images/Reliability.png)
- Company Age:-
  - Below is the code of calculating age of the company:-
  - `2024 - value.toNumber()`
    ![CompanyAge](/assests/images/CompanyAge.png)

## Part 2. Analyze Cleaned Data

- How many jobs listed by Nonprofit organization?

  - Answer - **19**
  - Steps:-
  - Create a Text facet on the Type of Ownership column.
  - Filter for "Nonprofit organization" within this facet.
  - The count displayed will indicate the number of jobs listed by Non-Profit Organization.

- Which state has the highest job openings?

  - Answer - **CA with count 37**
  - Steps:-
  - Create a Text facet on the State column.
  - It will display each state with job openings.
  - Then we can extract the highest job openings by checking the highest count.

- List the company name(s) that has the lowest reliability level?

  - Answer - **KeHE Distributors(2.5) and United BioSource(2.3)**
  - Steps:-
  - Create a Text facet on Reliabilty column and filter the lowest reliability level, in our case it is Good.
  - Select the Good level.
  - Then Create a Text facet on Company Name column so it will display company names with rating based on Good reliability level.
  - ![Low Reliability](/assests/images/Low%20Reliability.png)

- What type of job(s) advertised by companies headquartered in India?

  - Answer - **0**
  - Steps:-
  - Create a Text facet on Headquaters column.
  - It will display countries where the headquaters are there. So then filter out India.
  - Currently there are no headquaters in India.

- Name the Biggest industry by revenue and occurrence?
  - Answer - **Biotech & Pharmaceuticals**
  - Steps:-
  - Create a Text facet on Revenue column.
  - Check for the highest revenue, which is 10+ billion.
  - Then based on it text facet on Industry column.
  - It will display industries, we have to extract highest occurrence among these.

## References

- Cleaned Data [Cleaned Data](HW2-DSjobs.csv)
- Cleaned Data(JSON) [Json data](HW2-DSjobs.json)
- Images - [Images](./assests/images/)
