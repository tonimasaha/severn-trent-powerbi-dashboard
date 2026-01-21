# Operational Performance & SLA Risk Dashboard (Power BI)

A 3-page Power BI dashboard developed end-to-end as a portfolio project, using a synthetic dataset modelled on a UK utilities metering field operations use case (Severn Trent–style Metering Field Support). The report focuses on operational workload, SLA compliance, backlog monitoring, and trend-based risk indicators.

## Pages
### 1) Executive Overview
- High-level operational KPIs: Work Orders Total, Completed, Completion Rate, Backlog, Revisit Rate
- SLA performance KPIs: SLA Events Total, Breaches, Compliance %, Breach Rate %
- Global slicers: Date range, Region, Team (synchronised across all report pages)

### 2) Operational Performance
- Work Orders by Team (bar chart)
- SLA Breaches by Team (bar chart)
- Work Orders Trend over Time (line chart)
- SLA Breaches Trend over Time (line chart)
- SLA Event detail table with breach reasons and conditional formatting for rapid issue triage

### 3) Trends & Risk Indicators
- Rolling 3-month SLA breach trend to smooth volatility
- SLA Risk Status indicator (threshold-based) with conditional formatting
- Open work order backlog trend over time

## Data Model
- Star-schema data model with shared dimensions (Date, Team, Location, Job Type, Customer, Asset)
- Fact tables: Work Orders, SLA Events, Schedule, Customer Contacts
- Multiple date keys (Created, Completed, SLA Due) handled using active/inactive relationships and time-intelligence patterns

## Key KPIs (DAX)
- SLA Compliance %, SLA Breach Rate %
- Backlog (Open Work Orders)
- Rolling trends (3-month rolling SLA breaches)
- Risk thresholds implemented via status-based indicators

## Tools & Skills Demonstrated
- Power BI Desktop
- Data modelling (star schema, relationship design, filter context management)
- Power Query (M): data cleaning, category standardisation, missing value handling
- DAX: KPI measures, rolling windows, risk logic
- Dashboard design & UX: executive KPIs, operational drill-down, conditional formatting

## Design Notes & Modelling Decisions

- SLA analysis is performed at SLA-event grain, while workload analysis is performed at work-order grain.
- Multiple date relationships (Created, Completed, SLA Due) are present, with inactive relationships activated in DAX using USERELATIONSHIP where required.
- Team-level SLA breakdowns required explicit relationship activation to avoid ambiguous filter paths.
- A fact-based Team slicer is used for SLA drill-down to ensure reliable row-level filtering of SLA event detail tables.
- Rolling 3-month trend measures are used to smooth volatility and support proactive risk identification.

## Screenshots
| Executive Overview | Operational Performance | Trends & Risk |
|---|---|---|
| ![Page 1](screenshots/page-1-executive-overview.png) | ![Page 2](screenshots/page-2-operational-performance.png) | ![Page 3](screenshots/page-3-trends-risk.png) |

## Notes
This is a portfolio project built using synthetic data for demonstration purposes. The dashboard design was first wireframed and validated before being fully implemented in Power BI.
