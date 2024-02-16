# HW 3 - CS 625, Spring 2024

**Sanket Nadkarni**

Due: February 16, 2024

## Scatter Plot

### Data

**Indian startups funding in 2021.csv - Amount, Month and Sector**

- I trimmed down the big list of companies to include only those in the Computer Software sector. This step was important because it let us look closely at patterns and changes in this particular industry, which people who might want to invest in tech companies would find useful.
- I gathered the investment figures month by month to paint a clear picture of how funding changed over time. This method helps to spot ongoing trends and any regular ups and downs in investments, which can be useful for predicting future trends and making plans for investments.

### Visualization Idioms

Idiom: Area Chart
| Data: Attribute | Data: Attribute Type | Encode: Channel |
| --- |---| --- |
| Month | Temporal | Horizontal position on a common scale (x-axis) |
| Amount | quantitative | Vertical position on a common scale (y-axis) |
| Sector(Filter) | Categorical | Color hue |

- The area chart was a great fit because it showed how much money computer software sector got over time in a way that's easy to see. It's like drawing a line for the money received each month and then coloring in under the line to show increases and decreases, making it simple to spot when and how things changed for these companies.
- The x-axis represents Month, allowing us to track funding changes over time.
  The y-axis shows funding amounts (Quantitative), with larger amounts shown higher up.
  The sector is categorized as 'Computer Software'.

### Charts

![Monthly Funding Trends for Computer Software Startups in 2021](/assests/images/monthly%20funding%20trends.png)
Link to Tableau Workbook[Monthly Funding Trends for Computer Software Startups in 2021](./assests/Tableau/Monthly%20Funding%20Trends%20for%20Computer%20Software%20Startups%20in%202021.twb)
