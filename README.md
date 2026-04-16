# College Institution Selection Tool
### A Data-Driven Post-Secondary Decision Support Dashboard

Built with Tableau | Data: U.S. Department of Education (College Scorecard)

---

## Project Overview

This project presents an interactive Tableau dashboard designed to support data-driven college selection for an international student applicant with specific academic, financial, and geographic constraints. The tool integrates 
two institutional datasets to evaluate over 1,200 U.S. post-secondary institutions across five decision criteria simultaneously: academic competitiveness, financial affordability, and graduate earnings outcomes, program availability, and campus setting preference.

The dashboard is fully parameterized. Users enter their own SAT scores, maximum annual budget, enrollment preference, location type, and target states, and all visualizations update in real time to reflect only institutions where the applicant is academically eligible and financially able to attend.

---

## Student Profile

| Attribute | Detail |
|---|---|
| Name | Minnie Bui |
| Age | 17 |
| Nationality | Vietnamese (International Student) |
| GPA | 3.7 / 4.0 |
| SAT Score | 1380 / 1600 (Math: 700, Reading: 680) |
| Target Field | Actuarial Science / Applied Mathematics |
| Budget | Maximum $25,000 net cost per year |
| Preferred Setting | City or Rural campus |
| Preferred Size | 5,000 – 15,000 undergraduates |
| Geographic Preference | East or West Coast |

---

## Data Sources

| File | Description |
|---|---|
| `Nie_Institutional_Data.csv` | School-level characteristics including admission rate, cost, SAT distributions, enrollment, and locale |
| `Nie_Field_of_Study_Data.csv` | Program-level outcomes including graduate earnings and student debt by CIP code |

Both datasets are sourced from the U.S. Department of Education College Scorecard public dataset. The two tables are joined on `OPEID6`, the federal institution identifier, using a left join with the Institutional Data file as the primary table.

---

## Dashboard Features

### Interactive Parameters
- **SAT Math Score** — filters institutions where the applicant's math score meets or exceeds the school's 25th percentile floor
- **SAT Reading Score** — filters institutions where the applicant's reading score meets or exceeds the school's 25th percentile floor
- **Maximum Annual Budget** — dynamically filters and redraws the affordability reference line based on the user's cost ceiling
- **Locale Group** — toggle between City, Suburban, Town, and Rural settings
- **Pick State(s)** — filter to specific states or coastal regions
- **Total Undergraduate Enrollment** — range filter for campus size preference
- **Admission Rate** — minimum threshold filter for realistic applications

### Visualizations

**1. Affordability vs. Admission Likelihood**
Scatter plot positioning each institution by admission rate (x-axis) and net cost of attendance (y-axis). Color and shape encode SAT eligibility. A dynamic reference line marks the user's affordability threshold. The target zone highlights institutions that are both financially accessible and academically realistic.

**2. Tuition Investment vs. Graduate Earnings Outcomes**
Scatter plot comparing annual sticker price against median graduate earnings two years post-enrollment. Color encodes admission rate. A logarithmic trend line reveals that paying more does not proportionally increase earnings — supporting a value-focused application strategy.

**3. Business and Mathematics Programs and Campus Setting by Net Cost**
Dual-axis chart showing the percentage of students enrolled in mathematics (purple circles) and business (blue triangles) programs relative to net cost. Dot size encodes total undergraduate enrollment. Identifies institutions with genuine quantitative academic culture at an affordable price point.

**4. Institution List — Scored and Ranked**
Filtered data table displaying all institutions passing active filters, ranked by a composite Fit Score (0–100). Each row shows fit score, enrollment, annual cost, four-year completion rate, median debt, and graduate earnings. Color encodes fit tier: Best Fit, Target, Reach, or Not Ideal.

### Fit Scoring Model

The Fit Score is a composite metric calculated from four weighted criteria:

| Criteria | Max Points | Threshold |
|---|---|---|
| Admission Rate | 40 | ≥60% = 40pts, ≥40% = 25pts, else 10pts |
| Net Cost | 35 | ≤$18k = 35pts, ≤$25k = 20pts, else 10pts |
| Graduate Earnings | 15 | ≥$50k = 15pts, ≥$40k = 10pts, else 5pts |
| SAT Eligibility | 10 | Satisfied = 10pts, else 0pts |

| Score Range | Label | Meaning |
|---|---|---|
| 85 – 100 | Best Fit | All criteria strongly met |
| 65 – 84 | Target | Most criteria met |
| 50 – 64 | Reach | Some criteria fall short |
| Below 50 | Not Ideal | Multiple criteria not met |

---

## Key Findings

Based on the applicant profile with filters set to SAT Math 700, SAT Reading 680, maximum budget $25,000, city/rural setting, enrollment 5,000–15,000, admission rate 50–100%, and coastal state preference, the following institutions were identified as top recommendations:

| Priority | Institution | State | Fit Score | Net Cost | Grad Earnings |
|---|---|---|---|---|---|
| 1st Choice | University of Massachusetts Boston | MA | 100 | $24.9k | $58.5k |
| 2nd Choice | Augusta University | GA | 95 | $23.5k | $46.4k |
| 3rd Choice | Coastal Carolina University | SC | 95 | $26.7k | $41.5k |
| 4th Choice | Embry-Riddle Aeronautical University | FL | 85 | $24.9k | $65.6k |
| Backup | University of Houston Downtown | TX | 95 | $20.7k | $47.9k |

---

## Technical Details

| Tool | Usage |
|---|---|
| Tableau Desktop | Dashboard development and visualization |
| Tableau Parameters | Dynamic user input for SAT scores and budget |
| Calculated Fields | Fit Score, Fit Label, SAT Eligibility, Within Budget, Setting Match |
| Join Type | Left join on OPEID6 |
| Data Aggregation | AVG() for continuous measures at institution level |

---
## Skills Demonstrated

- Data joining and relationship modeling across multiple datasets
- Tableau calculated fields, parameters, and dynamic filtering
- Composite scoring model design and implementation
- Dashboard layout and interactive UX design
- Quantitative analysis and data-driven decision making
- Academic and professional technical writing

---

## Author

**May Bui**  
DePauw University
mayxbui@gmail.com
+1 (408) 303-8262

---

*Data sourced from the U.S. Department of Education College Scorecard. 
All analysis is for academic purposes.*
