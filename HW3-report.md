# HW 3 - CS 625, Spring 2024

**Sanket Nadkarni**

Due: February 16, 2024

## Area chart

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

## Area chart

### Data

**Comparison of Batting Average and Strike Rate for Cricket Batsmen for Top 25 Batsman - Average, Strike rate, Batsman, Total runs**

- I have checked the dataset for any missing or inconsistent values in the average and strikerate columns. And I have removed the null values using OpenRefine too. Where I used this GREL query
  `forEach(columns, c, if(isNull(cells[c].value), return(true), return(false))).some(v, v == true)`
  ![Unwanted Values](/assests/images/Averagecolumn.png)
- To focus on the top-performing batsmen, I have applied a filter to select only the top 25 batsmen based on a relevant metric such as total runs scored.

### Visualization Idioms

Idiom: Scatter Plot
| Data: Attribute | Data: Attribute Type | Encode: Channel |
| --- |---| --- |
| Average | quantitative | Horizontal position on a common scale (x-axis) |
| Strike rate | quantitative | Vertical position on a common scale (y-axis) |
| Batsman | Categorical | Label on Points |

- A scatter plot is suitable for comparing two quantitative variables, which in this case are batting average and strike rate. The scatter plot comparing batting average and strike rate for cricket batsmen offers cricket management valuable insights for player evaluation, team composition, strategic planning, and player development
- Each batsman is represented by a point on the plot, serving as an identifier
- The x-axis represents the batting average, allowing for a quantitative comparison across different players and the y-axis represents the strike rate.

### Charts

![Comparison of Batting Average and Strike Rate for Cricket Batsmen for Top 25 Batsman](/assests/images/Comparison%20of%20Batting%20Average%20and%20Strike%20Rate.png)

Link to Tableau workbook [Comparison of Batting Average and Strike Rate for Cricket Batsmen for Top 25 Batsman](./assests/Tableau/average%20and%20strikerate.twb)

## Bar chart using Tableau

### Data

**Toss Advantage: Do Winners of the Toss Also Win the Match?-Toss_decision, Toss-winner, winner**

- Creating a Calculated Field for Toss and Match Outcome Comparison named Toss_won_match to determine if the toss winner is the same as the match winner using formula-
  `IF [toss_winner] = [winner] THEN 'True' ELSE 'False' END`
- Only relevant columns were used for this analysis. Details such as player of the match, umpires, and venue might not contribute to the specific question at hand and were thus excluded to simplify the visualization and focus on the toss and match outcomes.
- The toss_decision field was included to group the data further, as it is a critical factor in understanding the strategic decisions teams make after winning the toss

### Visualization Idioms

Idiom: Grouped Bar Chart
| Data: Attribute | Data: Attribute Type | Encode: Channel |
| --- |---| --- |
| Toss_won_match | Categorical(Nominal) | Horizontal position on a common scale (x-axis) |
| Count of Matches | quantitative | Vertical position on a common scale (y-axis) |
| Toss Decision | Categorical(Nominal) | Color hue |

- The grouped bar chart clearly shows the comparison between two outcomes whether the toss-winning team won the match or not. This is easily interpreted as a binary True or False scenario.
- By grouping bars together based on the Toss Decision to bat or field, it allows for an additional layer of analysis within each toss and match win outcome.
- The use of color helps to immediately distinguish between the subcategories like toss decision to bat or field, making the chart instantly more informative

### Charts

![Toss Advantage: Do Winners of the Toss Also Win the Match?](/assests/images/Toss%20Advantage%20Do%20Winners%20of%20the%20Toss%20Also%20Win%20the%20Match.png)

Link to Tableau Workbook [Toss Advantage: Do Winners of the Toss Also Win the Match?](./assests/Tableau/Toss%20Advantage.twb)
