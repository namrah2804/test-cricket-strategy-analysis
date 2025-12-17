# Test Cricket Strategy Analytics (Case Study)

## 1. Project overview
This case study uses men’s Test match data (match-level and ball-by-ball) to explore what drives winning outcomes and how those insights can inform team strategy. The focus is on turning raw match data into guidance for selection, bowling combinations, and match tactics.

**Stakeholder scenario:**  
A Test team wants to improve results by grounding decisions in data rather than intuition. The project looks at:
- Squad selection
- Bowling attack composition by conditions
- Match tactics (e.g., toss/innings approach)

**Datasets:**
- Match-level: `data/match_level/tests_male_csv.zip`
- Ball-by-ball: `data/ball_by_ball/tests_male_csv2.zip`

**Key assumptions:**
- Only completed matches are analysed.
- Match result (win/loss/draw) is an appopriate performance outcome.
- Venue and conditions influence strategy decisions

 ---

## 2. Problems (to be validated with analysis)
### Problem 1: Strategy varies by venue, but decisions are often generic
**Hypothesis:** Some venues systematically favour batting first vs chasing / early seam vs spin, but decisions today are often “one size fits all”. 
**Evidence to add:** venue-wise results, innings patterns, toss decision outcomes.

### Problem 2: Player impact in Tests is not captured well by simple totals
**Hypothesis:** Consistency and “match impact” across innings matter more than one-off big performances, which basic aggregates miss.
**Evidence to add:** batter consistency metrics; bowler effectiveness metrics; impact in winning matches.

### Problem 3: Toss is over-valued without considering context
**Hypothesis:** Toss advantage is conditional on venue, season, and opposition, not a universal edge. 
**Evidence to add:** win% by toss winner overall and by venue.



---

## 3. Data and methods

### 3.1 Tools

- SQL: data preparation and KPI tables
- Python: exploratory analysis and custom visualisation
- R: statistical testing , modelling, visualisation
- Tableau: interactive dashboards and storytelling

### 3.2 Workflow

3.2.1 **Data preparation (SQL)**
- Load match-level and ball-by-ball Test data into relational tables.
- Standardise key fields (team names, venues, match results, toss decisions).
- Handle missing or inconsistent values where needed.

3.2.2 **Build KPI tables**
   - `venue_result.sql`: venue × result (win/loss/draw).
   - `toss_result.sql`: toss winner/decision × result.
   - `team_summary.sql`: team performance by venue, opposition, innings.
   - `player_aggregates.sql`: batting and bowling aggregates from ball-by-ball.

3.2.3 **Exploratory analysis and visuals ( Python)**
   - Explore distributions and trends (win percentages, innings totals, player aggregates).
   - Create comparative plots for venue and toss-related insights.
   - Develop reusable plotting functions to keep visuals consistent.
   - Use quick visual iterations to shape questions before dashboarding.

3.2.4. **Statistical Analysis and Advanced Visualisation (R)**
- Perform statistical tests (e.g. assessing whether toss advantage is statistically significant overall or venue-specific)
- Explore relationships between match variables and outcomes
- Create polished visualisations using `ggplot2` for clear communication of findings

3.2.5 **Tableau – Interactive Dashboards and Storytelling**

- Build dashboards summarising key findings from SQL, Python, and R outputs
- Present venue trends, toss impact, and team/player performance interactively
- Support executive-level exploration and decision-making

3.2.6 **Data Outputs and Reproducibility**

All cleaned datasets, KPI tables, and visual outputs will be stored in the `outputs/` and `visuals/` directories.  
This ensures reproducibility and enables seamless integration across SQL, Python, R, and Tableau as the project progresses.

---

## 4. Key findings (to be filled after analysis)
This section will summarise the main patterns discovered in the data, for example:

---

## 5. Strategy recommendations

### Option A: Venue-specific strategy playbook
**Pros:**  
-  
**Cons:**  
-  

### Option B: Selection framework based on consistency + match impact
**Pros:**  
-  
**Cons:**  
-  

### Option C: Toss decision rule by venue/conditions
**Pros:**  
-  
**Cons:**  
-  

---

## 6. Conclusion (to be written after analysis)
**Key takeaways:**  
-  
-  

---

## 7. Next steps
- Build SQL KPI tables and export results (`outputs/`)
- Create initial charts (venue and toss)
- Add evidence (numbers + visuals) back into this document

  ---
