# EMPLOYEE-ENGAGEMENT-AND-CULTURE
Employee engagement and organizational culture are critical drivers of productivity, retention, and innovation. This project leverages survey data to analyze engagement and culture metrics across departments, tenure groups, and locations, providing actionable insights for HR leadership
CALCULATED COLUMNS
1)Attrition = 
IF(
    'employee survey'[STATUS]IN {"Resigned", "Terminated", "Left"}, 
    1, 
    0
)
2)EngagementCategory = 
SWITCH(
    TRUE(),
    'employee survey'[ENGAGEMENT SCORE]>= 4, "High",
    'employee survey'[ENGAGEMENT SCORE] = 3, "Medium",
    'employee survey'[ENGAGEMENT SCORE]<= 2, "Low"
)

KPIS

Engagement KPIs

AvgEngagement = AVERAGE(EmployeeSurvey[EngagementScore])
PctHighlyEngaged = DIVIDE(COUNTROWS(FILTER(EmployeeSurvey, EmployeeSurvey[EngagementScore] >= 4)), COUNTROWS(EmployeeSurvey), 0)
AttritionRate = DIVIDE(COUNTROWS(FILTER(EmployeeData, EmployeeData[Status] = "Resigned")), COUNTROWS(EmployeeData), 0)

Culture KPIs

CultureIndex = AVERAGEX(EmployeeSurvey, (EmployeeSurvey[Collaboration] + EmployeeSurvey[Inclusion] + EmployeeSurvey[ValuesAlignment]) / 3)

Analyses Conducted

Descriptive Analysis:
Average engagement and culture scores by department, tenure, and location.
Distribution of employees across engagement categories (High, Medium, Low).
Comparative Analysis:
Cross-tab of engagement vs. culture rating.
Departmental differences in collaboration and inclusion.
Correlation Analysis:
Relationship between tenure and engagement (e.g., long-tenured employees more/less engaged).
Link between inclusion status and engagement score.
Text Analysis:
Thematic coding of comments (e.g., recognition, workload, leadership communication).
Segmentation:
Identify “at-risk” groups (low engagement, low culture rating).
Highlight “champion” groups (high engagement, strong collaboration).

This project demonstrates how structured employee survey data can be transformed into actionable insights. By analyzing engagement, culture, collaboration, and inclusion, organizations can identify problem areas and implement targeted solutions. The dashboard not only highlights current challenges but also serves as a continuous monitoring tool to track improvements over time.





