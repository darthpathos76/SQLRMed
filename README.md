DOWNLOAD THE CSV FILES https://drive.google.com/drive/folders/10ChGftl5l7HacdrP3v-Mwl2vvQ_acGcC?usp=drive_link 

## Description
Curious about SQL but not ready to dive into full-blown databases or external connections? This hands-on, beginner-friendly workshop is the perfect starting point. Using the lightweight and intuitive {sqldf} package in R, you’ll learn how to write SQL queries directly on your existing R data frames—no database setup required.

SQL (Structured Query Language) is a powerful tool for querying and transforming structured data, and it’s widely used in clinical research, data science, and industry analytics. In this 3-hour introductory session, we’ll bridge the gap between R and SQL in the most approachable way possible—by working with the data frames you already use in R.

We’ll cover:
What SQL is and why it’s useful alongside R
The basics of SQL syntax: SELECT, FROM, WHERE, ORDER BY, GROUP BY, and JOIN
How to use the {sqldf} package to run SQL queries on R data frames
Comparing SQL and dplyr for common data tasks
Writing readable, reusable SQL queries inside R scripts
This session is geared toward R users with little to no SQL experience. You’ll learn through guided examples and live coding, with time to practice writing your own queries. There’s no need for databases or complicated setup—just bring your laptop with R and {sqldf} installed, and we’ll take it from there.

By the end of the workshop, you’ll be able to:

Write SQL queries to filter, sort, group, and join data frames
Use {sqldf} to integrate SQL smoothly into your R scripts
Decide when SQL might be more effective than tidyverse functions (and vice versa)
Gain confidence in querying data more efficiently—even with large or complex datasets
This workshop is especially helpful for analysts, students, and researchers who want to become more versatile in handling data but prefer to stay within the comfort of the R environment. It’s also a great stepping stone for those who may later work with external databases (e.g., REDCap, EDC systems, or clinical trial platforms).

Come explore the power of SQL in a simple, approachable way—and learn to make your data talk.

## 🧑‍🏫 Who am I?

-   Background in clinical data systems (e.g., REDCap)
-   Advocate for *communication-first* data workflows
-   Goal: Make data more expressive, not just clean
-   When not up to my eyeballs in REDCap or R, I'm chasing my almost-6-year old     around the     park or listening to heavy metal 

:::notes
Hi everyone, I'm really excited to be here today.

Just a quick intro—my background is in clinical data systems, especially platforms like REDCap. I spend a lot of time working at the intersection of research, compliance, and technology.

One thing I really try to champion is communication-first data workflows. That means not just making sure the data is clean and valid—which is of course essential—but also making sure it’s understandable and actionable for the people who actually use it.

My goal is to make data more expressive—something that tells a story, not just something that passes a validation check.

And when I’m not up to my eyeballs in REDCap or R, you’ll probably find me chasing my almost-6-year-old around the park… or listening to way too much heavy metal.
:::

---

## Making Your Data Talk

**Section 0** - Learning the language<br>
**Section 1** - Listening to the Data<br>
**Section 2** - Understanding Relationships<br>
**Section 3** - Spotting patterns<br>
**Section 4** - Building the story<br>
**Section 5** - Compare and Reflect<br>
**Wrap-up and Next Steps**<br>
**Resources and Practice**<br>

:::notes
Here’s a quick overview of how we’ll move through the workshop today:

We’ll start with Section 0: Learning the language. This is where we get grounded in the terminology and structure of our data—making sure we all know what we’re working with.

Then in Section 1: Listening to the Data, we’ll look at how to let the data speak—focusing on summaries, distributions, and the kinds of questions the data is naturally ready to answer.

In Section 2: Understanding Relationships, we’ll dig into how variables connect—looking at joins, links across tables, and what those relationships mean.

Section 3 is Spotting Patterns. This is where we move beyond rows and columns and start seeing trends, clusters, or gaps—whether that's over time, across categories, or between groups.

Section 4 is Building the Story—how we translate analysis into insight. This is about communication: charts, visuals, and talking points that make your data easy to understand and act on.

In Section 5: Compare and Reflect, we’ll step back and look at what we’ve done—comparing outcomes, methods, and thinking critically about what we’ve learned.

Then we’ll move into the Wrap-up and Next Steps, where I’ll highlight practical ways you can apply this back in your own projects.

And finally, I’ll leave you with a set of Resources and Practice tools you can use to keep building on what we covered today.
:::
---

## Section 0: Learning the Language

Good data tells the truth. Great data tells a story.

:::notes
I want to start with a guiding principle I come back to over and over again:

Good data tells the truth.
Great data tells a story.

Good data is clean, complete, and technically sound. It passes validation. It lines up in the database. It gives us the facts — and that’s essential.
But facts on their own aren’t always enough.

Because good data might tell you what happened — but great data tells you why it matters.

Great data has structure, yes — but it also has voice. It has clarity. It leads someone — a clinician, a researcher, a decision-maker — from confusion to understanding, and ideally, to action.

And that’s really the goal of today’s session. Not just to clean the data, or validate the form, or merge the tables.
But to listen to what the data is telling us — to find the patterns, the relationships, the signals — and then shape that into something meaningful.

So as we go through each section, I want you to keep that in mind.
We’re not just working with variables. We’re working with potential stories.
Your job — our job — is to help those stories come through.
:::

### Understanding SQL and Your Data

#### 💡 Why SQL?

-   SQL = Structured Query Language
-   Used to **query structured/tabular data**
-   Complements R — helps answer *relational* questions
-   Portable and expressive — used across industries

:::notes
So before we dive in, let’s talk about why SQL matters in this context.

SQL stands for Structured Query Language. It’s the standard language used to work with structured, tabular data — the kind of data we see in REDCap exports, clinical databases, and most spreadsheets or flat files.

What makes SQL so powerful is that it’s designed for asking questions — especially relational questions.
Things like:

How do these two tables connect?

What happened before and after this event?

Which records meet this specific condition?

In that sense, SQL complements R really well.
R is fantastic for analysis, modeling, and visualization.
SQL is great for organizing and extracting the data you want to work with before you do all that.

And here’s the best part — SQL is portable.
Whether you're working with REDCap data, a hospital system, an EHR, a data warehouse, or even Excel files loaded into R — SQL is used across all of them.
So if you learn it here, you can apply it almost anywhere.

Bottom line: SQL helps you get the right data in the right shape for the job. And once you have that, everything else flows a lot more smoothly.
:::

#### 📜 A Brief History

-   Developed at IBM in the 1970s (Boyce & Chamberlin)
-   Based on E.F. Codd’s relational model
-   ANSI standard since 1986 — still widely used

:::notes
I always think it helps to know where tools like SQL come from — especially something that’s been around this long and is still going strong.

SQL was originally developed at IBM in the 1970s by Donald Chamberlin and Raymond Boyce. They were building on the work of E.F. Codd, who introduced the idea of the relational model — a way of thinking about data in terms of tables, rows, and relationships between them.

That model became the foundation for most modern databases, and SQL was the language designed to interact with those systems.

By 1986, SQL had become so widely adopted that it was formalized as an ANSI standard, and it’s still one of the most widely used data languages today — across industries, platforms, and systems.

What’s impressive is that while the syntax has evolved a bit over the decades, the core principles behind SQL haven’t changed much. The idea of selecting, filtering, grouping, and joining data is just as relevant now as it was in the early days — whether you’re working in a healthcare setting, doing research, or building software.
:::

---

## Section 0 (cont’d): Theory & Definitions

#### ✅ What SQL *Is* and *Isn’t*

| SQL **Is**             | SQL **Isn’t**                |
|------------------------|------------------------------|
| Declarative            | A programming language       |
| Optimized for tables   | Suited for unstructured data |
| Readable and shareable | Built for graphics/models    |
| Great with joins       | Less flexible than R         |

:::notes
I think it’s really helpful to set expectations upfront — to be clear about what SQL is, and what it isn’t. Because sometimes people come to SQL expecting it to behave like a programming language, or like R, and then get frustrated when it doesn’t.

So let’s break it down:

On the left, SQL is declarative. That means you don’t tell it how to do things — you just describe what you want: 'Give me all the rows where age is over 65' or 'Sum these values grouped by county.'
You’re describing the result, and the database engine figures out the steps.

It’s also optimized for tabular data — anything that fits neatly into rows and columns. Think spreadsheets, REDCap exports, databases.
It’s incredibly good at that.

It’s also very readable and easy to share. SQL code is closer to plain English than most other tools — which makes it a great choice when you're collaborating or documenting your workflow.

And finally, SQL is great with joins — which is one of its superpowers. If you're working with data across multiple tables or forms, SQL is probably the cleanest way to link it all together.

Now, on the right — here’s what SQL isn’t:

It’s not a full programming language. You can’t build an app or a simulation or a full data pipeline in SQL alone. You’ll usually pair it with something else — like R or Python — to get the full picture.

It’s not ideal for unstructured data — like free text, images, or PDFs. You can store that kind of data in a database, but querying it gets tricky.

It’s not built for graphics or statistical models — that’s where R really shines. SQL will give you the right slice of data, but R is what you use to visualize it and dig deeper.

And finally, it’s less flexible than R. It’s powerful within its domain — but it’s not meant to do everything.

So think of SQL as your starting point: it helps you extract and shape your data, so you can analyze, visualize, and tell the story more effectively with tools like R.
:::

---

## 🧠 Core Concepts

| Term       | Purpose             |
|------------|---------------------|
| `SELECT`   | Choose columns      |
| `FROM`     | Choose table        |
| `WHERE`    | Filter rows         |
| `ORDER BY` | Sort rows           |
| `GROUP BY` | Aggregate/summarize |
| `JOIN`     | Merge data          |

:::notes
Now that we know what SQL is and isn’t, let’s break down some of the core building blocks you’ll use every day.

Think of these as the fundamental commands that let you ask your data exactly what you want.

SELECT: This is how you choose which columns — or variables — you want to see in your output.
For example, you might want just the patient ID and total charges, not every single column.

FROM: This tells SQL which table to look in.
If you think of your data as a spreadsheet, this is where you say which sheet to pull from.

WHERE: This is how you filter rows — basically, select only the records that meet a condition.
For example, only patients older than 65, or only records from a certain county.

ORDER BY: This lets you sort your results.
Maybe you want to see the highest charges first or sort patients alphabetically by last name.

GROUP BY: This is a key command for aggregation or summarization.
It lets you group rows based on one or more columns, so you can get sums, averages, or counts for each group.

JOIN: This is how you merge data from multiple tables — like connecting patient info from one table with lab results in another.
Joins are essential for combining relational data.

These core commands form the backbone of almost every SQL query you’ll write. As we go on, we’ll see them in action with real data examples.
:::

---

## 📦 Setup and a sample query 

``` r
install.packages("sqldf")
library(sqldf)
hospital <- read.csv("hospital_data_nyc.csv")
sqldf("SELECT DISTINCT facility_name, age_group FROM hospital LIMIT 5")
```
``` {r}
library(sqldf)
hospital <- read.csv("hospital_data_nyc.csv")
sqldf("SELECT DISTINCT facility_name, age_group FROM hospital LIMIT 5")
```

:::notes
Let’s look at a quick example of how to use SQL right inside R with the sqldf package.

First, you need to install the package if you haven’t already — you can do that with:

r
install.packages("sqldf")
Once it’s installed, load the package using:

r
library(sqldf)
Here, I’m loading a CSV file called hospital_data_nyc.csv — this is a sample dataset with hospital records.

Then, using sqldf(), I write a SQL query directly as a string inside R.

This query:

sql
SELECT DISTINCT facility_name, age_group FROM hospital LIMIT 5
Selects distinct combinations of facility name and age group from the hospital data,

And limits the output to just 5 rows so it’s easy to look at.

Using sqldf is really handy because it lets you leverage familiar SQL syntax to quickly filter, summarize, and explore your data, all within your R workflow — no separate database needed.

You can try this yourself by running these lines in your R console or script.
:::

---

## Section 1: Listening to the Data

### Exploring NYC Hospital Procedures

-   Use `SELECT`, `WHERE`, `ORDER BY`
-   Answer basic questions:
    -   Top 5 hospitals by procedure type
    -   Most common procedures
    -   Highest charges by Age and Race

:::notes
Now that we’ve covered some basics, let’s apply those SQL skills to explore real-world data from NYC hospitals.

In this section, we’ll focus on three key SQL commands:

SELECT to pick the columns we want,

WHERE to filter rows based on conditions, and

ORDER BY to sort our results.

Our goal is to answer some practical questions, like:

Which are the top 5 hospitals by procedure type?

What are the most common procedures performed?

And how do charges vary by patient Age and Race?

These questions are typical of the kinds of insights clinical data managers, analysts, and researchers need to extract regularly.

By the end of this section, you’ll see how combining these SQL commands can quickly surface valuable insights from complex datasets.
:::
    
---

### Top 5 Hospitals by volume

``` r
sqldf("SELECT facility_name, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY facility_name
       ORDER BY freq DESC 
       LIMIT 5")
```

``` {r}
sqldf("SELECT facility_name, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY facility_name
       ORDER BY freq DESC 
       LIMIT 5")
```

:::notes
Let’s walk through this query step-by-step:
sqldf("SELECT facility_name, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY facility_name
       ORDER BY freq DESC 
       LIMIT 5")
First, SELECT facility_name, COUNT(*) as freq tells SQL to return each hospital’s name, along with a count of how many records or procedures they have in the data — this count is labeled as freq for frequency.

Next, FROM hospital specifies the dataset we’re querying.

Then, GROUP BY facility_name groups all the rows by hospital name, so the counts are calculated per hospital.

ORDER BY freq DESC sorts the results by frequency, from highest to lowest, so the busiest hospitals come first.

Finally, LIMIT 5 restricts the output to only the top 5 hospitals by procedure count.

Running this gives us a quick look at which hospitals perform the most procedures in our dataset — a useful summary for workload or resource planning.
:::

---

### Most common procedures
``` r
sqldf("SELECT ccsr_procedure_description, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY ccsr_procedure_description 
       ORDER BY freq DESC 
       LIMIT 5")
```

``` {r}
sqldf("SELECT ccsr_procedure_description, COUNT(*) as freq FROM hospital GROUP BY ccsr_procedure_description ORDER BY freq DESC LIMIT 5")
```

:::notes
Now, let’s shift our focus to procedures themselves.

This query:
sqldf("SELECT ccsr_procedure_description, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY ccsr_procedure_description 
       ORDER BY freq DESC 
       LIMIT 5")
Uses SELECT to pull the procedure descriptions alongside the count of how often each procedure appears, labeling that count as freq.

FROM hospital tells SQL to use our hospital dataset.

GROUP BY ccsr_procedure_description groups records by procedure type, so we get a frequency for each distinct procedure.

ORDER BY freq DESC sorts the results so the most frequent procedures appear at the top.

And LIMIT 5 restricts output to just the top five procedures.

This gives us a snapshot of the most common procedures performed across all hospitals in the dataset — a valuable insight for understanding procedure volume and resource allocation.
:::

--- 

### Highest charges by Age and Race
``` r
sqldf("SELECT race, age_group, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY race, age_group 
       ORDER BY freq DESC 
       LIMIT 5")
```

``` {r}
sqldf("SELECT race, age_group, COUNT(*) as freq FROM hospital GROUP BY race, age_group ORDER BY freq DESC LIMIT 5")
```
:::notes
Next, let’s explore how charges vary across different demographic groups — specifically by Age and Race.

Here’s a query that groups the data by race and age group, counting the number of records in each group:
sqldf("SELECT race, age_group, 
              COUNT(*) as freq 
       FROM hospital 
       GROUP BY race, age_group 
       ORDER BY freq DESC 
       LIMIT 5")
Breaking it down:

We’re selecting the columns race and age_group, alongside a count of how many records fall into each combination — labeled as freq.

The data is grouped by both race and age group, so we get frequencies for each demographic subgroup.

We then order the results by frequency in descending order, so the groups with the highest number of records come first.

Finally, the output is limited to the top 5 groups.

While this query counts the frequency, we can modify it to sum up total_charges for these groups to better understand where the highest charges occur.

This kind of breakdown is key for uncovering disparities or patterns in healthcare utilization and costs.
:::

---

## Section 2: Understanding Relationships

### SQL Joins: Relating Tables in Your Data

| Join Type         | Description                                      |
|-------------------|--------------------------------------------------|
| `INNER JOIN`      | Only rows with matching keys in both tables      |
| `LEFT JOIN`       | All rows from the left table, with matches from the right (if any) |
| `RIGHT JOIN`¹     | All rows from the right table, with matches from the left (if any) |
| `FULL OUTER JOIN`¹| All rows from both tables, matched where possible |
| `CROSS JOIN`      | Every combination of rows from both tables       |

> ¹Note: `{sqldf}` only supports `INNER JOIN` and `LEFT JOIN`. Other types require a full SQL engine (e.g., PostgreSQL or full SQLite

:::notes
One of the foundational strengths of SQL is the ability to combine data from multiple tables through what we call joins. In real-world datasets, information is often spread across different tables — for example, patient demographics might be in one table, procedures in another, and billing details in yet another. Joins let us bring these pieces together to get a complete picture.

Let’s walk through the main types of joins you’ll encounter:

INNER JOIN
This join returns only the rows where there is a matching key in both tables.
Imagine you have a table of patients and a table of hospital visits. An inner join on patient ID will give you only those patients who actually have visit records. If a patient has no visits, they won’t appear in the results. This is useful when you want to focus only on entities with related data in both tables.

LEFT JOIN
This one returns all rows from the left table, plus any matching rows from the right table.
If there’s no match, you still get the left table’s row, but with missing (NULL) values for the right table columns.
For example, if you want a list of all patients regardless of whether they had visits, you’d do a left join from the patients table to visits. This helps in identifying patients without any visits.

RIGHT JOIN
This is basically the mirror image of a left join — it returns all rows from the right table, plus matching rows from the left.
It’s less commonly used but handy in some scenarios. However, a quick heads-up: {sqldf}, the R package we’re using for SQL, does not support right joins.

FULL OUTER JOIN
This join returns all rows from both tables, matching where possible, and filling in missing data with NULLs where there is no match.
It’s like combining a left and right join, ensuring nothing is left out.
This is especially useful when you want a comprehensive view of all records from both tables, even if they don’t align perfectly.

CROSS JOIN
This join returns every possible combination of rows between the two tables — a Cartesian product.
It’s rarely used directly because it can produce huge datasets quickly, but it’s useful for generating combinations or testing.

Important note: When using the {sqldf} package in R — which we’ll be working with — you only have access to INNER JOIN and LEFT JOIN.
More advanced joins like RIGHT JOIN or FULL OUTER JOIN require a full SQL engine such as PostgreSQL, MySQL, or a complete SQLite installation outside of {sqldf}.

Mastering joins is essential because your data will almost never be in a single flat table. Being able to relate tables effectively unlocks much richer and more insightful analyses.
:::

---

### Joining with County Info

-   Load `hosptial_nyc_counties.csv`
-   Practice `LEFT JOIN`

``` r
counties <- read.csv("hosptial_nyc_counties.csv")
sqldf("SELECT h.facility_name, 
              c.hospital_county 
       FROM hospital h INNER JOIN counties c ON h.hospital_county = c.county_id 
       LIMIT 10")
```

``` {r}
counties <- read.csv("hosptial_nyc_counties.csv")
sqldf("SELECT h.facility_name, c.hospital_county FROM hospital h INNER JOIN counties c ON h.hospital_county = c.county_id LIMIT 10")
```
:::notes
Now that we’ve learned about joins in theory, let’s put it into practice with our hospital dataset.

We’ll start by loading an additional CSV file called hospital_nyc_counties.csv. This file contains information about counties — essentially, geographic areas linked to the hospitals.
counties <- read.csv("hosptial_nyc_counties.csv")

Once we have both datasets loaded (hospital and counties), we can combine them using a join. Here, the goal is to link each hospital record to its corresponding county name.

The SQL query we’re using is:
SELECT h.facility_name, c.hospital_county
FROM hospital h
INNER JOIN counties c ON h.hospital_county = c.county_id
LIMIT 10

Breaking it down:

We select the hospital’s name (facility_name) from the hospital table alias h.

We also select the hospital_county field from the counties table alias c.

The INNER JOIN connects these tables where the hospital’s county ID matches the county’s ID.

LIMIT 10 restricts the output to just 10 rows so we can quickly verify the join results.

This join is crucial because it enriches our hospital data with geographic context, enabling us to perform analyses based on location.

Practicing joins like this lays the foundation for integrating multiple data sources to build more comprehensive datasets for deeper insights.
:::

---

### Identify which counties see the most discharges

``` r
sqldf("SELECT c.hospital_county,
              SUM(h.total_charges) AS Total_Charges
       FROM hospital h INNER JOIN counties c ON h.hospital_county = c.county_id
       GROUP BY c.hospital_county
       ORDER BY Total_Charges DESC")
```

``` {r}
sqldf("SELECT 
    c.hospital_county,
    SUM(h.total_charges) AS Total_Charges
  FROM hospital h
  INNER JOIN counties c
    ON h.hospital_county = c.county_id
  GROUP BY c.hospital_county
  ORDER BY Total_Charges DESC
")
```

:::notes 
Let’s now analyze which counties are associated with the highest total charges — a useful way to understand healthcare resource utilization across regions.

Here’s the SQL query we’re using:
SELECT c.hospital_county,
       SUM(h.total_charges) AS Total_Charges
FROM hospital h
INNER JOIN counties c ON h.hospital_county = c.county_id
GROUP BY c.hospital_county
ORDER BY Total_Charges DESC

Breaking it down:

We’re selecting the county name from the counties table (aliased as c), which gives us the geographic grouping.

We use the SUM() function on total_charges from the hospital table (aliased as h) to calculate the total charges aggregated per county.

The INNER JOIN ensures that we only include hospital records matched to valid counties.

GROUP BY groups the data by county, so the sum is calculated per county.

Finally, ORDER BY Total_Charges DESC sorts the results from highest to lowest total charges, making it easy to identify the counties with the largest healthcare expenditures.

This kind of analysis helps administrators and policymakers understand where the greatest healthcare costs are concentrated, which can guide resource allocation and planning.
:::

---

## Section 3: Spotting Patterns

### Summarizing and Grouping

-   Use `GROUP BY`, `AVG()`, `COUNT()`
-   Explore:
    -   Avg. cost per county
    -   Conditions by demographic

``` r
sqldf("SELECT ccsr_diagnosis_description, 
              AVG(length_of_stay) as avg_days 
       FROM hospital 
       GROUP BY ccsr_diagnosis_description 
       ORDER BY avg_days DESC 
       LIMIT 5")
```

``` {r}
sqldf("SELECT ccsr_diagnosis_description, 
      AVG(length_of_stay) as avg_days 
      FROM hospital 
      GROUP BY ccsr_diagnosis_description ORDER BY avg_days DESC LIMIT 5")
```

:::notes 
In this section, we focus on how to summarize data and spot meaningful patterns by grouping records and calculating averages or counts.

We use SQL’s powerful aggregation functions — such as GROUP BY, AVG(), and COUNT() — to explore insights hidden in the data.

For example, here’s a query that finds the average length of stay by diagnosis:
SELECT ccsr_diagnosis_description, 
       AVG(length_of_stay) as avg_days 
FROM hospital 
GROUP BY ccsr_diagnosis_description 
ORDER BY avg_days DESC 
LIMIT 5

Breaking this down:

We select the diagnosis description and calculate the average number of days patients stayed in the hospital for each diagnosis.

The GROUP BY clause groups the data by diagnosis, so the average length of stay is computed for each group.

We then order the results by the average length of stay in descending order, to highlight diagnoses associated with the longest hospital stays.

Finally, we limit the output to the top 5 diagnoses for easier interpretation.

This approach helps identify which conditions tend to require longer hospitalizations — information that can be critical for hospital management, patient care planning, and resource allocation.

In addition to average length of stay, similar methods can be used to explore average costs per county or condition prevalence by demographic groups, helping us spot important patterns across the data.
:::

---

## Section 4: Building the Story

### From Query to Visualization

-   Use output of SQL in `plotly`

``` r
library(plotly)
summary_df <- sqldf("SELECT c.hospital_county, 
                            race, 
                            SUM(h.total_charges) as total_charges 
                     FROM hospital h INNER JOIN counties c 
                         on h.hospital_county = c.county_id 
                     GROUP BY c.hospital_county, race 
                     HAVING count(*)>10000 
                     ORDER BY c.hospital_county, race")


plot_ly(summary_df, 
        x = ~hospital_county, 
        y = ~total_charges, 
        color = ~race, 
        type = 'bar',
        hoverinfo = 'text+y')
```
---

``` {r}

library(plotly)
summary_df <- sqldf("SELECT c.hospital_county, race, SUM(h.total_charges) as total_charges FROM hospital h INNER JOIN counties c on h.hospital_county = c.county_id GROUP BY c.hospital_county, race HAVING count(*)>10000 ORDER BY c.hospital_county, race")


plot_ly(summary_df, 
        x = ~hospital_county, 
        y = ~total_charges, 
        color = ~race, 
        type = 'bar',
        hoverinfo = 'text+y')
```
:::notes
Now that we’ve extracted meaningful summaries with SQL, it’s time to build the story visually.

Data visualization turns raw numbers into insights that are easier to understand and communicate. Here, we’re using the plotly package in R to create an interactive bar chart.

First, we run an SQL query that aggregates total hospital charges by county and race:
SELECT c.hospital_county, race, SUM(h.total_charges) as total_charges
FROM hospital h
INNER JOIN counties c on h.hospital_county = c.county_id
GROUP BY c.hospital_county, race
HAVING count(*) > 10000
ORDER BY c.hospital_county, race

This query groups the data by county and race, calculating the sum of charges for each group. The HAVING count(*) > 10000 filters to include only groups with significant data volume, which helps avoid noisy or unreliable results.

Next, we feed the resulting summary dataframe into plot_ly() to create a grouped bar chart:

The x-axis shows the counties.

The y-axis shows the total charges.

The bars are colored by race to compare different groups within each county.

Hover info displays detailed values for better interactivity.

This approach helps us spot disparities or trends in charges across demographic groups and geographic regions — a powerful way to tell the story hidden in the data.

Interactive plots like this also let users drill down and explore the data dynamically, making the findings more accessible.


Key Observations:

Charges vary significantly by race across counties.

Bronx and Queens see the highest charges for Other Race, while Manhattan and Richmond see the highest for White.

Black/African American charges tend to be lower across most counties except for Kings.

Implications:

These patterns may reflect disparities in healthcare access, cost structures, or utilization across racial groups.

The data can inform healthcare equity efforts and policy decisions aimed at addressing systemic differences.

Conclusion: This visualization highlights racial disparities in healthcare costs across hospital counties, providing insights for further study and intervention.
:::

---

``` r
library(plotly)
summary_df <- sqldf("SELECT c.hospital_county, 
                            race, 
                            age_group, 
                            AVG(h.total_charges) as total_charges 
                     FROM hospital h INNER JOIN counties c 
                        on h.hospital_county = c.county_id 
                     GROUP BY c.hospital_county, race, age_group 
                     HAVING count(*)>10000 
                     ORDER BY c.hospital_county, race, age_group")


plot_ly(summary_df, 
        x = ~hospital_county, 
        y = ~total_charges, 
        color = ~race, 
        type = 'bar',
        text = ~paste("Age Group:", age_group),
        hoverinfo = 'text+y')
```

:::notes
In this example, we extend our data storytelling by incorporating multiple demographic factors into a single visualization.

First, we use an SQL query to summarize the data:

We join the hospital and counties tables to get geographic context.

We group the data by county, race, and age group to calculate the average total charges for each subgroup.

The HAVING count(*) > 10000 clause ensures we only include groups with sufficient data, improving the reliability of our results.

Results are ordered by county, race, and age group for clear organization.

Next, we visualize this summary using Plotly’s interactive bar chart:

The x-axis represents hospital counties.

The y-axis shows the average total charges.

Bars are colored by race, allowing comparison between racial groups within each county.

Hover text shows the corresponding age group, providing additional context without cluttering the main view.

This visualization allows us to explore patterns in healthcare charges across multiple dimensions — geography, race, and age — all in one place. While this chart shows the age group info on hover, further enhancements like faceting by age group or stacking bars could provide even clearer insight.

Interactive plots like this help stakeholders quickly grasp complex multi-dimensional data and support data-driven decisions.
:::
---

``` {r}

library(plotly)
summary_df <- sqldf("SELECT c.hospital_county, race, AVG(h.total_charges) as avg_charges FROM hospital h INNER JOIN counties c on h.hospital_county = c.county_id GROUP BY c.hospital_county, race HAVING count(*)>10000 ORDER BY c.hospital_county, race")


plot_ly(summary_df, 
        x = ~hospital_county, 
        y = ~avg_charges, 
        color = ~race, 
        type = 'bar',
        hoverinfo = 'text+y')
```

:::notes
Key Observations:

Manhattan has the highest average hospital charges across all racial groups.

Richmond has the lowest average charges for Other Race and Black/African American.

Across most counties, White patients tend to have higher average charges compared to other groups.

Implications:

The variation in hospital charges by county and race may reflect differences in healthcare costs, services provided, or insurance coverage.

Understanding these disparities can help in assessing healthcare equity and identifying possible systemic barriers to access.

Conclusion: This visualization highlights racial disparities in average hospital charges, providing a foundation for further discussion and policy development around healthcare cost fairness.

So to take these two graphs and to tell a story looking at the various graphs and queries:

Black/African American patients tend to have both lower total and average hospital charges across most counties. This could reflect limited access to care, fewer hospital visits, or disparities in the intensity of treatment received.

Other Race patients show high total charges in areas like the Bronx and Queens, likely due to higher hospital usage. However, their average charges per visit are relatively low, suggesting frequent visits for lower-cost care.

White patients typically have higher average charges per visit, possibly indicating access to more expensive treatments or better insurance coverage. In counties like Manhattan and Richmond, they also show high total charges, suggesting both frequent use and higher-cost care.

Takeaway:
These patterns suggest that race is closely linked to healthcare access and cost. Disparities may stem from systemic factors such as insurance, income, or provider behavior — highlighting the need for more equitable healthcare policies and practices.
:::

---

## Section 5: Compare + Reflect

### SQL vs. dplyr

-   Rewrite SQL queries in `dplyr`
-   Strengths of each:
    -   SQL: better for joins and grouped summaries
    -   dplyr: easier piping, chaining, readable logic

``` r
library(dplyr)
hospital %>% group_by(diagnosis) %>% summarise(n = n()) %>% arrange(desc(n))
```
:::notes 
In this section, we look at how SQL compares with dplyr, one of R's most popular packages for data manipulation.

Both are incredibly useful tools — and rather than thinking of them as competing, it’s helpful to see them as complementary.

SQL excels at:

Handling relational data — especially joins across tables.

Summarizing large datasets inside databases.

Being portable across platforms — from SQLite to PostgreSQL.

dplyr, on the other hand:

Uses the pipe (%>%) syntax, which makes logic easier to follow, especially when you're transforming data step-by-step.

Is more intuitive for many R users, especially when exploring or wrangling data in-memory.

The example here mirrors a basic SQL GROUP BY and ORDER BY:
hospital %>%
  group_by(diagnosis) %>%
  summarise(n = n()) %>%
  arrange(desc(n))

This gives us the most common diagnoses in the dataset — the same logic as a SQL SELECT diagnosis, COUNT(*) FROM hospital GROUP BY diagnosis ORDER BY COUNT(*) DESC.

Ultimately, your choice depends on what you're doing:

If you're inside R and working with one dataset — dplyr may feel more natural.

If you're pulling from multiple tables or need to query a database directly — SQL is still your best friend.
:::
---

## Wrap-Up & Next Steps

-   What did we learn?
    -   SQL helps *ask* and *frame* data questions
    -   `{sqldf}` is an easy bridge from R to SQL
    -   Joins = relationships = context
-   Next steps:
    -   Try connecting SQL to other datasets (REDCap, EDCs)
    -   Learn about full relational databases (e.g., PostgreSQL)

:::notes
Let’s take a moment to summarize what we’ve covered:

First, we learned how SQL helps us frame the right questions. It gives us the structure to think clearly about the relationships in our data — which is critical for clinical and operational decision-making.

We saw how {sqldf} makes it easy to bring SQL into R — letting us tap into SQL’s strengths without leaving the R environment.

We also explored how joins create context. By linking tables like hospital data with county information, we enrich our dataset and uncover deeper stories.

As for next steps:

If you're working with REDCap or other EDCs, try connecting SQL queries to those datasets. Even if you're exporting CSVs, many of the same principles apply.

And if you’re ready for more power and flexibility, consider diving into full relational databases like PostgreSQL or MySQL. These systems support more advanced SQL features and can handle larger, more complex datasets.

Ultimately, the goal is to use SQL not just to clean data, but to understand it — and tell better, more meaningful stories
:::
---

## Resources & Practice

-   Cheat sheet: SQL basics
-   Practice queries
-   SPARCS + counties dataset (subset)
-   `sqldf` documentation

> "Good data tells the truth. Great data tells a story."

:::notes
🔚 Closing Remarks
Today, we explored SQL not just as a technical tool, but as a gateway to meaning. You saw how {sqldf} lets us frame questions, connect data across tables, and surface patterns that might otherwise stay buried. You practiced translating structured clinical data into insights—and that process is where real impact begins.

But beyond syntax and summaries, there’s something more important at stake.

🧭 Why Storytelling Matters in Clinical Research
"Good data tells the truth. Great data tells a story."

In clinical research, the “truth” often lies in rows and columns—coded values, cost fields, discharge records. But the “story” lives in why those numbers matter: who they represent, what they reveal, and how we can act on them.

Every record represents a person. A patient. Someone who came into a hospital, had a procedure, faced uncertainty, and left behind a trace in a dataset. When we analyze this data—whether to study utilization, cost, equity, or outcomes—we’re entrusted with a powerful responsibility.

And storytelling is how we give back.

When we tell the story well, we honor the people behind the data.

When we see disparities, we have a chance to advocate.

When we translate findings into action, we close the loop—from data, to insight, to impact.

🛠️ Resources & Practice
To keep the momentum going, explore these resources:

✅ Cheat sheet – SQL building blocks and examples

✅ Practice queries PDF – 15 hands-on exercises to hone your skills

✅ SPARCS + counties subset – Real-world NYC hospital data for testing

✅ sqldf documentation – Learn how to use SQL within R seamlessly

💬 Final Thought
This is why we do what we do. Clinical data analysis isn’t just numbers—it’s narrative. And your job, as a data practitioner or researcher, is to surface meaning, communicate with purpose, and always remember who the data comes from.

Let your work tell a story. Let that story serve.
:::
