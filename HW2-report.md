# HW 2 - CS 625, Spring 2024

**Sanket Nadkarni**

Due: January 31, 2024

## Part 1 - Data Cleaning

- Loaded the DataSet into OpenRefine.
- Remove row/columns:-
  - Removed all blank rows/columns by running command :-
    `if(isBlank(cells['Job Title'].value), 'remove', if(cells['Job Title'].value == '-1', 'remove', value))`
  - Editing the values in the column:-
    To get the highest value for column size:-
    - `if(isBlank(value), "0", value.split(" ")[-2])`. This will get us the last value which will be the highest.
      ![Highest value](/assests/images/HighestValue.png)
  - Creating a new column:-
    - In location column dropdown, I selected Add column based on this column option. So a new column will be created with values same as location column and I named it State. Then I used this command to extract state name from location :- `value.split(",")[1].trim()` as the data is stored in "City, State" format.
    - Then rename the location column as City. And for extracting only city name used this command :- `value.split(",")[0].trim()`.
  - Creating Relability Column:-
    - Below is the code for each criteria on rating column:-
      `if(value == null, "Unknown", if(value <= 2, "OK", if(value <= 2.5, "Good", if(value <= 3.5, "Very Good", "Excellent"))))`
      ![Reliability](/assests/images/Reliability.png)
  - Company Age:-
    - Below is the code of calculating age of the company:-
      `2024 - value.toNumber()`
      ![CompanyAge](/assests/images/CompanyAge.png)
