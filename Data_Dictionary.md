# 📚 Formula 1 Race Intelligence - Data Dictionary

This data dictionary outlines the metadata, column descriptions, data types, and business logic for the **6,464 race records** dataset across 17 Formula 1 seasons (2007–2023).

| Column Name | Data Type | Sample Value | Description |
| :--- | :--- | :--- | :--- |
| `Race_ID` | Integer | `1` | Unique numerical identifier for each Grand Prix race session. |
| `Season` | Integer | `2021` | Formula 1 World Championship championship year (range: 2007–2023). |
| `Round` | Integer | `1` | Race calendar order index within that season. |
| `Grand_Prix` | String | `Monaco Grand Prix` | Official name of the Grand Prix race event. |
| `Circuit_Name` | String | `Circuit de Monaco` | Name of the racing track / circuit. |
| `Circuit_Type` | String | `Street Circuit` | Track typology: `Street Circuit`, `High-Speed / Power`, or `High-Downforce / Technical`. |
| `Country` | String | `Monaco` | Host nation where the Grand Prix took place. |
| `Driver_Name` | String | `Lewis Hamilton` | Full name of the participating driver. |
| `Driver_Nationality` | String | `British` | Nationality of the driver. |
| `Constructor_Name` | String | `Mercedes` | Racing team / constructor entry. |
| `Grid_Position` | Integer | `1` | Qualifying starting position on the grid (1 to 20). |
| `Finishing_Position`| String | `1` or `DNF` | Final classified race position (1–20) or `DNF` if incomplete. |
| `Points` | Decimal | `25.0` | World championship points awarded for the finishing position. |
| `Status` | String | `Finished` | Official race status: `Finished`, `+1 Lap`, `Engine`, `Brakes`, `Collision`, etc. |
| `DNF_Category` | String | `Classified Finish` | Standardized failure category: `Classified Finish`, `Engine Failure`, `Brake Failure`, `Collision / Incident`, `Mechanical Failure`. |
| `Tyre_Compound` | String | `Medium` | Primary tyre compound strategy utilized: `Soft`, `Medium`, `Hard`, `Intermediate`. |
| `Laps_Completed` | Integer | `78` | Total laps completed by the driver during the race session. |
| `Podium_Finish` | Integer (0/1) | `1` | Binary flag indicating if the driver finished in top 3 (`1` = Yes, `0` = No). |
| `Race_Completion_Flag` | Integer (0/1) | `1` | Binary flag indicating if the race was successfully completed (`1` = Classified, `0` = DNF). |
