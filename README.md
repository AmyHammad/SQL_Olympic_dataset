# Olympics SQL Analysis 🏅

This project explores **120 years of Olympic history** using SQL.  
The dataset comes from [Kaggle]

### Questions Answered
- How many Olympic games have been held?
- Which year saw the highest and lowest number of countries participating?
- Which nation has participated in all Olympic games?
- Who are the top 5 athletes by medals won?
- Which sports were only played once?

### Tech Stack
- SQL Server (MSSQL)
- Data: `athlete_events.csv`, `noc_regions.csv`

### Repo Structure
- `queries/` → all SQL queries grouped by topic
- `results/` → exported results for selected queries
- `data/` → dataset (or Kaggle link)

---

### Sample Query
```sql
-- Fetch the top 5 athletes who have won the most gold medals
SELECT
    name,
    team,
    COUNT(*) AS gold_medals
FROM athlete_events
WHERE medal = 'Gold'
GROUP BY name, team
ORDER BY gold_medals DESC
LIMIT 5;
