# UK Road Accident Analysis Dashboard

An interactive **Power BI dashboard** for exploring road traffic accidents through severity, casualties, vehicle involvement, road conditions, weather, lighting, and location-related factors.

The project turns a structured accident dataset into a visual report that helps users explore patterns, compare conditions, and ask more focused questions about road safety.

## Dashboard Preview

![UK Road Accident Analysis Dashboard](https://github.com/XERA-03/Uk-Road-Accident-Analysis-/blob/main/Dashboard.png?raw=true)

> **Dashboard screenshot:** [View Dashboard.png](https://github.com/XERA-03/Uk-Road-Accident-Analysis-/blob/main/Dashboard.png)

## Project Motivation: Why Analyse Road Accidents?

Road accidents are not just numbers in a spreadsheet. Each record represents an incident that can involve injuries, disruption, and costs for individuals and communities. However, a dataset with thousands of rows can be difficult to interpret by reading it record by record.

The motivation for this project was to make accident data easier to explore and to practise how data analytics can support evidence-informed road-safety discussions. A dashboard can help an analyst examine questions such as whether accident counts vary by road-surface condition, weather, lighting, road type, severity, or time. It can also help users compare casualties with accident counts rather than relying on a single headline figure.

This is an **exploratory analytics project**, not a claim that the dashboard proves why crashes happen or predicts future accidents. The visualisations show patterns in the available data; they do not establish causation. The workbook is used as the project's analysis dataset, and this README does not claim that the underlying accident records were originally collected or created by the author.

## Objectives

- Summarise accident records and casualty-related measures in one report.
- Compare accidents by severity, weather, road surface, road type, lighting, and urban/rural setting.
- Explore the number of casualties and vehicles involved.
- Make filtering and comparison easier through Power BI visuals and slicers.
- Practise a complete BI workflow: understanding data, building measures, designing visuals, and communicating insights.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Power BI Desktop** | Interactive dashboard and data visualisation |
| **Power Query** | Data inspection and transformation where required |
| **DAX** | Measures and calculated metrics |
| **Microsoft Excel (.xlsx)** | Dataset storage and inspection |
| **GitHub** | Project documentation and versioned project files |

## Repository Contents

| File | Description |
|---|---|
| `Dashboard.png` | Screenshot preview of the finished dashboard |
| `UK ACCIDENT DASHBOARD.pbix` | Power BI report file; open it in Power BI Desktop |
| `Uk Accident Dataset.xlsx` | Excel workbook used for the analysis |
| `README.md` | Project overview and documentation |

## Dataset Overview

The Excel workbook contains a sheet named `Sheet1` and includes **19 columns** describing accident records.

| Column | Description |
|---|---|
| `Accident_Index` | Identifier recorded for an accident |
| `Accident Date` | Date of the accident |
| `Day_of_Week` | Day-of-week category in the source data |
| `Junction_Detail` | Junction type or detail |
| `Accident_Severity` | Recorded severity category |
| `Latitude`, `Longitude` | Geographic coordinates, where available |
| `Light_Conditions` | Lighting condition at the time |
| `District` | District/location category |
| `Number_of_Casualties` | Number of casualties recorded |
| `Number_of_Vehicles` | Number of vehicles involved |
| `Police_Force` | Police-force category in the dataset |
| `Road_Surface_Conditions` | Recorded road-surface condition |
| `Road_Type` | Road-type category |
| `Speed_limit` | Recorded speed limit |
| `Time` | Time of the accident |
| `Urban_or_Rural_Area` | Urban/rural classification |
| `Weather_Conditions` | Recorded weather condition |
| `Vehicle_Type` | Vehicle-type category |

**Data note:** Consult the source dataset's original documentation for its provenance, date coverage, geographic coverage, collection methodology, and permitted reuse. Those details should not be inferred from column names alone. Before publishing derived findings, check for missing values, duplicate identifiers, date/time consistency, and any filtering applied in Power BI.

## Dashboard Features

The report is designed to support the following types of exploration:

- **Accident overview:** a headline view of accident records and related measures.
- **Accident severity:** compare the distribution of recorded severity categories.
- **Casualty analysis:** review casualty totals and the relationship between casualty counts and accident counts.
- **Vehicle involvement:** explore the number of vehicles involved in reported accidents.
- **Weather conditions:** compare accident records across weather categories.
- **Road surface conditions:** inspect how records are distributed across surface categories.
- **Road characteristics:** analyse by road type, junction detail, and speed limit.
- **Lighting conditions:** compare records across light conditions.
- **Location context:** explore district and urban/rural categories, with coordinates available in the workbook.
- **Interactive filtering:** use the available report slicers/filters to focus the view on selected categories or periods.

The exact metrics and visuals displayed depend on the measures and filters implemented in the `.pbix` file.

## Key Questions This Dashboard Can Help Explore

1. How are accident records distributed across severity categories?
2. How many casualties are recorded, and how does that compare with accident counts?
3. Which weather and road-surface categories contain the most recorded accidents?
4. How do accident records differ by road type, lighting, and urban/rural area?
5. What patterns appear when the data is filtered by date, district, or other available categories?
6. How many vehicles are recorded as involved in the accidents being analysed?

These are analytical questions, not pre-established findings. The results should be read from the dashboard and validated against the underlying dataset.

## How to Open the Project

1. Download or clone this repository.
2. Install **Microsoft Power BI Desktop**.
3. Open `UK ACCIDENT DASHBOARD.pbix`.
4. If Power BI asks for the data source, point it to `Uk Accident Dataset.xlsx` in the location where you saved the workbook.
5. Review the data model, Power Query steps, measures, and report pages.
6. Use the slicers and filters to interact with the report.

### Clone the repository

```bash
git clone https://github.com/XERA-03/Uk-Road-Accident-Analysis-.git
cd Uk-Road-Accident-Analysis-
```

## Analytical Approach

A typical workflow for this project is:

1. **Inspect the dataset** — review column names, data types, missing values, duplicates, and category consistency.
2. **Prepare the data** — confirm that dates, times, numeric measures, and categories use suitable types.
3. **Define measures** — distinguish accident counts, casualty totals, vehicle totals, averages, and rates.
4. **Build visuals** — select charts that suit comparisons, distributions, and time-based analysis.
5. **Add filters** — allow users to narrow the analysis by available date, location, or condition fields.
6. **Validate results** — compare Power BI totals with independently calculated totals from the workbook.
7. **Communicate carefully** — describe observed patterns without presenting correlation as causation.

### Metric definitions to keep clear

- **Accident count:** count of accident records or distinct accident identifiers, depending on the model's grain.
- **Total casualties:** sum of `Number_of_Casualties`.
- **Total vehicles involved:** sum of `Number_of_Vehicles`, if each row represents an accident and the field is stored at that level.
- **Average casualties per accident:** total casualties divided by the number of distinct accidents in the selected filter context.
- **Casualties per day:** interpret carefully; the calculation should specify whether it means average casualties per calendar day in the selected period or casualties on each date.

The calculation method should match the grain of the dataset. If the workbook has more than one row per accident, a simple row count or sum may double-count records. Confirm the data model before relying on the metrics.

## Limitations

- The dashboard is descriptive and exploratory; it does not by itself identify causal relationships.
- The quality of the analysis depends on the accuracy, completeness, definitions, and coverage of the source data.
- Missing values, inconsistent category labels, duplicated records, and different reporting practices can affect results.
- Accident counts alone do not measure risk fairly across areas or conditions. Exposure measures—such as traffic volume, distance travelled, or time spent on the road—may be needed for meaningful risk comparisons.
- A high number of accidents in one category does not automatically mean that category is intrinsically more dangerous; the amount of road use and other factors may differ.
- This report should not be treated as an official operational safety assessment or as a substitute for professional investigation.

## Future Improvements

- Add a documented source citation and data dictionary for the workbook.
- Include data-quality checks and a clear record of transformation steps.
- Add a date table and validated time-trend measures.
- Add maps or geographic drill-downs where coordinates are reliable and appropriate.
- Compare accident counts with exposure data to support more meaningful risk analysis.
- Add a methodology page explaining metric definitions, exclusions, and limitations.
- Include accessibility improvements such as readable contrast, descriptive titles, and alternative text.

## Author

**Satya Ranjan Jena**  
GitHub: [@XERA-03](https://github.com/XERA-03)

## Disclaimer

This repository is an educational and portfolio data-analytics project. It is intended for exploratory analysis and demonstration of Power BI skills. Interpret results in the context of the dataset's documentation and limitations.

---

If you find this project useful, feel free to explore the report and dataset files in the repository.
