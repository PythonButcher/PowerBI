# Power BI Court Analytics Project State

## Page 1

Power BI Court Analytics Project State
Objective
Build a realistic Court CMS analytics environment using PostgreSQL and Power BI.
Goals:
Learn Power BI from beginner through advanced features.
Develop a portfolio-quality analytics solution.
Create realistic operational data that supports meaningful reporting.
Use PostgreSQL as the primary source system.
Continuously expand the dataset as new reporting ideas emerge.
Current Architecture
Source System
PostgreSQL Court CMS database.
Core entities include:
Cases
Charges
Hearings
Payments
Warrants
Pleas
Dispositions
Sentences
People
Attorneys
Judges
Courts
Offenses
Case Status
Case Types
Power BI Model
Fact Tables:
FactCases
FactCharges• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
1


## Page 2

FactHearings
FactPayments
FactPleas
FactDispositions
FactSentences
FactWarrants
Bridge Tables:
BridgeCaseParty
Dimension Tables:
DimDate
DimCaseStatus
DimCaseType
DimCourts
DimJudge
DimPerson
DimOffense
DimAttorney
DimPleaType
Measures Table:
Case Count
Charge Count
Hearing Count
Payment Count
Person Count
Warrant Count
Active Warrant Count
Sentence Count
Total Payment Amount
Additional ratio measures
Important Model Decisions
Date Modeling
Auto Date/Time disabled.
Single DimDate table is used.
FactCases filing date relationship is the primary active relationship.• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
2


## Page 3

Other date relationships use USERELATIONSHIP().
Report Design Philosophy
Avoid dashboard-first development.
Build:
Data
Model
Measures
Analysis
Visuals
in that order .
Major Discovery
The largest current bottleneck is not Power BI.
The bottleneck is data realism.
Randomly generated records create visually flat reports.
Useful analytics requires intentional business behavior .
Data Engineering Strategy
Create realistic operational patterns.
Traffic Offense
Characteristics:
Highest volume
Highest payment activity
Few hearings
High closure rate
Criminal Misdemeanor
Characteristics:
Moderate hearings1. 
2. 
3. 
4. 
5. 
• 
• 
• 
• 
• 
3


## Page 4

Moderate warrants
Balanced lifecycle
Criminal Felony
Characteristics:
Highest warrant rate
Most hearings
Long case duration
More appeals
Family Law
Characteristics:
Long lifecycle
Frequent hearings
Large active caseload
General Civil
Characteristics:
High closure rate
Moderate duration
Probate/Estate
Characteristics:
Long duration
Low volume
Few warrants
Juvenile
Characteristics:
High diversion rate
Lower volume
Current Case Distribution
Target operational distribution:
Traffic Offense = 900• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
4


## Page 5

Criminal Misdemeanor = 700
Family Law = 550
General Civil = 350
Criminal Felony = 250
Probate/Estate = 150
Juvenile = 100
Next Data Expansion Phase
Generate realistic relationships between entities:
Cases → Charges
Cases → Hearings
Cases → Payments
Cases → Warrants
Charges → Pleas
Charges → Dispositions
Dispositions → Sentences
The goal is to create data that naturally supports:
KPI Cards
Trends
Drillthrough
Decomposition Tree
Key Influencers
Time Intelligence
Executive Reporting
Operational Reporting
without requiring artificial Power BI workarounds.
Known Lessons Learned
A refresh failure exposed an incorrect date relationship.
FactPayments[payment_date] was incorrectly configured on the "one" side of a relationship.• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
• 
5


## Page 6

Resolution:
DimDate[Date] must be the one side.
FactPayments[payment_date] must be the many side.
This validated that the data pipeline and model are functioning correctly.
Current Focus
Continue expanding the PostgreSQL dataset before investing heavily in report visuals.
The immediate priority is creating realistic court system behavior rather than creating additional Power BI
measures or pages.
6

