Automation Flow

Status: setup in progress — this doc will be updated with confirmed refresh timings and a screen recording once live.

Goal

Update the source Excel file → Power BI report reflects the change without manually reopening Power BI Desktop or republishing.

Setup
Source Excel file (credit_risk_dataset.xlsx) is stored in OneDrive, not a local folder — required for Power BI Service to schedule refreshes against it.
The Power BI report is connected to that OneDrive file via Power Query (Get Data → Excel).
The report is published to Power BI Service (My Workspace).
In Power BI Service, the dataset's Scheduled Refresh is configured to check the OneDrive file on a recurring schedule.
Flow
Excel file updated (OneDrive)
        ↓
Power BI Service scheduled refresh picks up the change
        ↓
Published report reflects updated data
        ↓
(No manual refresh, re-publish, or file re-upload needed)
Planned extension

A Power Automate flow ("When a file is modified" trigger on the OneDrive file → "Refresh a dataset" action) to make the refresh event-driven instead of time-based, so updates reflect near-instantly rather than waiting for the next scheduled window.

Content
