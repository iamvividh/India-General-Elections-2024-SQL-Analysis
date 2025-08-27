# India General Elections 2024 – SQL Analysis

## Project Overview

This project analyzes the **India General Elections 2024** dataset using SQL. The analysis focuses on understanding election outcomes across constituencies, states, parties, and alliances. The goal is to derive insights into seat distribution, party performance, alliance strengths, candidate victories, and voting patterns.

The project uses **five tables**:

1. `constituencywise_results` – Constituency-level results
2. `constituencywise_details` – Candidate-level details including votes
3. `partywise_results` – Party-wise performance
4. `statewise_results` – Mapping of constituencies to states
5. `states` – State information

## Query Index

The SQL queries in this project address the following analytical questions:

1. What is the **total number of seats** in the election?
2. How many **seats are available in each state**?
3. What is the **total number of seats won by NDA alliance**?
4. How many seats did each **NDA party win individually**?
5. What is the **total number of seats won by I.N.D.I.A alliance**?
6. How many seats did each **I.N.D.I.A party win individually**?
7. How can we **categorize parties into alliances (NDA, I.N.D.I.A, OTHER)** in the database?
8. Who were the **winning candidates**, their parties, vote totals, and victory margins in a specific constituency?
9. What is the **distribution of EVM vs Postal votes** in a specific constituency?
10. Which parties won the most seats in a **given state**, and how many?
11. What is the **total number of seats won by each alliance (NDA, I.N.D.I.A, OTHER) per state**?
12. Which candidates received the **highest number of EVM votes** (Top 10 across constituencies)?
13. Who were the **winner and runner-up candidates** in each constituency of a given state?
14. For Maharashtra, what are the **total seats, candidates, parties, EVM votes, postal votes, and total votes**?
15. How can we combine the above analyses to get a **comprehensive national and state-level view** of the 2024 election results?

## Key Insights

* Provides a **multi-dimensional view** of the elections at national, state, party, and candidate levels.
* **Alliance performance** analysis highlights regional strengths and weaknesses.
* Candidate-level queries reveal **close contests** and significant victory margins.
* **EVM vs Postal vote analysis** shows key differences across constituencies.
* Maharashtra was studied in detail, offering insights into seats, votes, and party representation.

## Entity-Relationship Diagram

```text
+--------------------------------+        +-------------------------+
|      partywise_results (pr)    |        |        states (s)       |
|--------------------------------|        |-------------------------|
| Party_ID (PK)                  |<-----+ | State_ID (PK)           |
| Party                          |      | | State                  |
| Won                            |      | +-------------------------+
| party_alliance                 |      |
+--------------------------------+      |
                                        |
+--------------------------------+      |
| constituencywise_results (cr)  |      |
|--------------------------------|      |
| Constituency_ID (PK)           |------+-----> statewise_results (sr)
| Parliament_Constituency        |      |
| Party_ID (FK)                  |      |
| Winning_Candidate              |      |
| Total_Votes                    |      |
| Margin                         |      |
+--------------------------------+      |
        |                               |
        |                               |
        v                               v
+--------------------------------+   +-----------------------------+
| constituencywise_details (cd)  |   |   statewise_results (sr)    |
|--------------------------------|   |-----------------------------|
| Constituency_ID (FK)           |   | Parliament_Constituency     |
| Candidate                      |   | State_ID (FK)               |
| Party                          |   +-----------------------------+
| EVM_Votes                      |
| Postal_Votes                   |
| Total_Votes                    |
+--------------------------------+
```

## Files in Repository

* **SQL Queries** → `ELECTIONS_SQL_Queries.pdf`
* **Raw Data Files**:

  * `constituencywise_results.csv`
  * `constituencywise_details.csv`
  * `partywise_results.csv`
  * `statewise_results.csv`
  * `states.csv`

## Conclusion

This project demonstrates the use of SQL for **exploratory data analysis (EDA)** on the 2024 Indian General Election dataset. The queries collectively uncover patterns in alliance strength, party performance, candidate outcomes, and voting behaviors. These findings form a strong foundation for further visualization and predictive analysis using BI tools such as Power BI or Tableau.
