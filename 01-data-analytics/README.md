# **PitWall Analytics**

Pontificia Universidad Javeriana _·_ Data Visualization _·_ May 2026 _|_ Sara Sofía Robayo Negrete

**1,125 thousand 861 212 75 42.3% 22.1%**

Races Analyzed · Unique Drivers · Constructors · Seasons (1950–2024) · Pole _→_ Win Conversion Rate · Mechanical Failure Rate

## **1,125 thousand**

### **Key Findings**

### **Conclusions**

- **Ferrari leads the all-time rankings** with more than 240 victories, followed by McLaren (182) and Mercedes (125). The area chart reveals clear dominance cycles: Ferrari in the 2000s, Red Bull between 2010–2013, and Mercedes between 2014–2021.

- **Pole position is advantageous but not decisive.** The pole _→_ win conversion rate is 42.3%; in more than 57% of races, the winner started from second position or further back, highlighting the decisive role of race strategy.

- **Monaco and Phoenix have the lowest comeback index**, with negative values of up to _−_ 8 positions on average. On narrow street circuits, starting position is practically decisive in determining the final result.

- **Historical mechanical failure rate: 22.1%.** This reflects the sport's technological evolution: mechanical retirement rates in the 1950s–1970s exceeded 50%, while in the modern era they are below 10%.

- **British drivers lead in victories by nationality**, with more than 300 historical wins, followed by German drivers (214) and Brazilian drivers (101), confirming the United Kingdom's historical importance in Formula 1.

- **Monza is the most diverse circuit in terms of winners**, with approximately 40 different drivers having won there throughout its history. This contrasts with modern circuits where team dominance significantly reduces winner diversity.

- **A robust, relational data source.** The _Formula 1 World Championship (1950–2024)_ dataset from Kaggle, containing 14 CSV files linked through primary and foreign keys, provided a solid foundation for building a sophisticated BI model.

- **An efficient star schema.** With `results` as the fact table and four dimensions (`drivers`, `constructors`, `races`, `circuits`), the model addressed all five visualization objectives, including the two involving multiple data sources (Objectives 3 and 5).

- **Feature engineering was essential.** The columns _Finalizo_, _Falla Mecánica_, _Accidente_, and _RemontadaF_, together with specialized DAX measures, enabled visualizations that could not have been built directly from the raw data.

- **Race strategy is as relevant as qualifying performance.** The finding that 57.7% of victories occurred without pole position suggests that customer teams should balance investment in qualifying performance with pit stop strategy planning.

- **High user satisfaction during validation:** 4.6/5 for clarity, 4.8/5 for visual design, and a 100% recommendation rate. Subsequent adjustment: reducing visual density on pages containing multiple charts.

- **Formula 1's global expansion** is visible on the geographical map: from a historically European concentration to an increasing presence in Asia, the Middle East, and the Americas, a trend that has intensified since 2010.

### **Results Analysis**

The results provide a coherent narrative of Formula 1's evolution across 75 seasons. The cyclical dominance of Ferrari, Red Bull, and Mercedes is immediately visible in the area chart on Page 3.

The qualifying analysis (Objective 3), combining Dataset 1 with Dataset 2, reveals a positive correlation between starting position and race result, but with considerable dispersion: pit stop strategy (Objective 4) can reverse up to 8 positions on favorable circuits.

The geographical map (Objective 5) confirms the sport's historical concentration in Europe and its recent expansion into the Middle East and the Americas.

Overall, **PitWall Analytics** demonstrates that open Formula 1 data can generate actionable insights for teams, media outlets, and fantasy racing platforms.

---

PitWall Analytics _·_ Pontificia Universidad Javeriana _·_ Data Visualization _·_ 2026

# **PitWall Analytics — Executive Appendix**

Visualization Objectives _·_ Validation Results _·_ Strategic Recommendations

### **Project Visualization Objectives**

| **#** | **Objective** | **Main Indicator** | **Datasets** | **Multi-source** |
|---|---|---|---|---|
| 1 | **Historical driver performance** | Pole _→_ win conversion rate (42.3%) | DS1 | No |
| 2 | **Constructor analysis** | Constructor reliability index (% of races completed) | DS1 | No |
| 3 | **Impact of qualifying on race results** | Average comeback index by circuit | DS1 + DS2 | **Yes** |
| 4 | **Pit stop strategy** | Correlation between pit stops and final position by circuit | DS3 | No |
| 5 | **Geographical analysis of victories** | Winner diversity index by circuit | DS1 + DS3 | **Yes** |

### **User Validation Results**

### **Strategic Recommendations**

A structured survey was conducted with five users (classmates, Formula 1 fans, and users with no BI experience). The survey included seven Likert-scale questions (1–5) and one dichotomous question.

| **Evaluation Aspect** | **Average Score** |
|---|---:|
| Clarity of purpose | **4.6 / 5** |
| Chart interpretability | 3.8 / 5 |
| Filter usability | 4.2 / 5 |
| Visual design | **4.8 / 5** |
| Information usefulness | 4.2 / 5 |
| Would recommend the tool | **100% Yes** |

#### **Adjustments Made Following User Validation**

- Reduced visual density by removing redundant elements from pages containing multiple charts simultaneously.
- Reorganized time filters to make it easier to explore specific season ranges.
- Prioritized the most relevant charts on each page, improving the overall interpretability of the report.

Based on the project's findings, the following recommendations are proposed for PitWall Analytics' customers:

- **For constructor teams:** Investing in pit stop strategy can deliver returns comparable to improvements in qualifying performance. The fact that 57.7% of victories occurred without pole position confirms that races can be won (or lost) in the pit lane.

- **For street circuits** (Monaco, Baku, Las Vegas): The priority should be maximizing qualifying performance, given that the comeback index is structurally negative on these tracks.

- **For specialized media outlets:** The winner diversity index by circuit is a powerful storytelling indicator that can enrich historical editorial coverage and provide context for current seasons.

- **For fantasy racing platforms:** The pole _→_ win conversion rate (42.3%) and constructor reliability index (22.1% historical mechanical failure rate) are high-value predictive variables for scoring models.

- **Next steps:** Incorporate 2025 data once available through the Ergast/OpenF1 API and expand the lap time analysis (`lap_times.csv`) to model tire degradation by circuit.

### **Data Sources and Technologies Used**

| **Component** | **Details** | **Purpose in the Project** |
|---|---|---|
| **Main dataset** | _F1 World Championship 1950–2024_ (Kaggle, rohanrao) | 14 CSV files containing race results, drivers, constructors, and circuits |
| **BI Tool** | Microsoft Power BI Desktop | Data modeling, ETL (Power Query), DAX, and interactive visualization |
| **Data Model** | Star Schema | `results` as the central fact table with four dimensions |
| **API Source** | Ergast Motor Racing Data API | Foundation of the Kaggle dataset; enables updates with future seasons |
| **Validation** | Google Forms (survey of 5 users) | Evaluation of clarity, usability, and dashboard design |

---

PitWall Analytics _·_ Pontificia Universidad Javeriana _·_ Data Visualization _·_ 2026
