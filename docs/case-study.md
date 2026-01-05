# Test Cricket Strategy Analytics (Case Study)

## 1. Project overview

The analysis uses publicly available men’s Test match data sourced from Cricsheet.  
The datasets cover international Test matches played between all major cricketing nations, spanning from the beginning of Test cricket in 1877 up to matches played in 2025.

Two datasets are used:
- A match-level dataset containing summary information such as teams, venues, match results, and toss decisions
- A ball-by-ball dataset containing delivery-level details to support deeper player and performance analysis

**Project goal**
The main goal is to understand how venue, conditions, and opposition influence match outcomes and to translate those patterns into strategy recommendations that teams can use for:

- Squad selection
- Bowling attack composition by conditions
- Match tactics (e.g., toss/innings approach)

While the framework can be applied to any Test team, the initial analysis focuses on England as a case study team — evaluating its performance at home and abroad against different opponents.
Insights, however, are generalisable to other teams, enabling comparative analysis across nations.

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
**Goal:** Identify venue‑specific performance trends to inform pre‑match decisions and team selection.

### Problem 2: Player impact in Tests is not captured well by simple totals
**Hypothesis:** Consistency and “match impact” across innings matter more than one-off big performances, which basic aggregates miss.
**Evidence to add:** batter consistency metrics; bowler effectiveness metrics; impact in winning matches.
**Goal:** Build player impact indices that measure both consistency and contextual importance, aiding in evidence‑based selection.

### Problem 3: Toss is over-valued without considering context
**Hypothesis:** Toss advantage is conditional on venue, season, and opposition, not a universal edge. 
**Evidence to add:** win% by toss winner overall and by venue.
**Goal:** Develop a toss decision framework that identifies when it truly matters and when other factors dominate outcomes.


---

## 3 **Scope and segmentation:**
To ensure depth and flexibility, the analysis will be segmented along key dimensions:

- By team: each major Test nation (with England as the main example).
- By venue: home vs away performance, country‑specific ground conditions.
- By opposition: variations in win rate and player impact against specific teams.
- By condition: pitch type, climatic zone, and seasonality.

This allows comparisons such as:

“How does England’s bowling attack perform in Australia versus India?”
“Does the toss matter more in subcontinental conditions than in seaming climates?”

These comparisons will form the empirical base for later recommendations.

---

## 4. Data and methods

### 4.1 Tools

- SQL: data preparation and KPI tables
- Python: exploratory analysis and custom visualisation
- R: statistical testing , modelling, visualisation
- Tableau: interactive dashboards and storytelling

### 4.2 Workflow

4.2.1 **Data preparation (SQL)**
- Load match-level and ball-by-ball Test data into relational tables.
- Standardise key fields (team names, venues, match results, toss decisions).
- Handle missing or inconsistent values where needed.

4.2.2 **Build KPI tables**
   - `venue_result.sql`: venue × result (win/loss/draw).
   - `toss_result.sql`: toss winner/decision × result.
   - `team_summary.sql`: team performance by venue, opposition, innings.
   - `player_aggregates.sql`: batting and bowling aggregates from ball-by-ball.

4.2.3 **Exploratory analysis and visuals ( Python)**
   - Explore distributions and trends (win percentages, innings totals, player aggregates).
   - Create comparative plots for venue and toss-related insights.
   - Develop reusable plotting functions to keep visuals consistent.
   - Use quick visual iterations to shape questions before dashboarding.

4.2.4. **Statistical Analysis and Advanced Visualisation (R)**
- Perform statistical tests (e.g. assessing whether toss advantage is statistically significant overall or venue-specific)
- Explore relationships between match variables and outcomes
- Create polished visualisations using `ggplot2` for clear communication of findings

4.2.5 **Tableau – Interactive Dashboards and Storytelling**

- Build dashboards summarising key findings from SQL, Python, and R outputs
- Present venue trends, toss impact, and team/player performance interactively
- Support executive-level exploration and decision-making

4.2.6 **Data Outputs and Reproducibility**

All cleaned datasets, KPI tables, and visual outputs will be stored in the `outputs/` and `visuals/` directories.  
This ensures reproducibility and enables seamless integration across SQL, Python, R, and Tableau as the project progresses.

---

## 5. Key findings (to be filled after analysis)
This section will summarise the main patterns discovered in the data, for example:

---

## 6. Strategy recommendations

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

## 7. Conclusion (to be written after analysis)
**Key takeaways:**  
-  
-  

---

## 8. Next steps
- Build SQL KPI tables and export results (`outputs/`)
- Create initial charts (venue and toss)
- Add evidence (numbers + visuals) back into this document

  ---
