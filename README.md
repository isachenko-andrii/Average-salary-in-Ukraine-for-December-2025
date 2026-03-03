![Project-logo](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/Project-logo.png)
<div align="center">  
    
## Average Salary in Ukraine for December 2025<br>(Data visualization with Power BI)   
  
</div>

## Project Description  
  
This project is dedicated to the visualization and analysis of the average wage level by region in Ukraine as of December 2025. The main goal is to identify economic disparities between regions and present the data in a user-friendly format using Power BI.  

## Tools  
  
* **Visualization:** Power BI Desktop  
* **Cartography:** Custom TopoJSON map (for accurate representation of regional boundaries)  
* **Data sources:** [Ministry of Finance (index.minfin.com.ua)](https://index.minfin.com.ua/ua/labour/salary/average/)  
* **Data formats:** JSON (geodata), Excel (statistics)  

## Main features of the dashboard  
  
1. **Interactive map of Ukraine:** Color indication of income levels for each region.  
2. **Comparative analysis:** Ability to quickly identify leading regions and regions with the lowest indicators.  
3. **Tooltips:** When hovering over a region, the exact amount and deviation from the average indicator are displayed.  

## How to view the project  
  
1. Download the `project.pbix` file from this repository.  
2. Open it using [Power BI Desktop](https://powerbi.microsoft.com/desktop/).  
- additionally download the map of Ukraine (Ukraine-regions.json) and the file with salary data (szp.xlsx, to download the data correctly, place the file on your desktop)  
3. The project is available at the link.  

## Key findings (Insights)  
  
* **Kyiv** remains the leader in terms of income, which is due to the high concentration of service and IT companies.  
* There is a positive trend in the western regions due to the development of logistics hubs.  
* The abnormally high average salary in the Luhansk region in 2025 (which may even be higher than Kyiv's) is a classic statistical outlier caused by specific factors.  
  
## Repository structure  
  
Average-salary-in-Ukraine-for-December-2025/  — Project data  
├── data/ — Project data  
├── images/ — Project screenshots  
├── Ukraine-regions.json — is the map file used for visualization  
├── Project.pbix —  is the main file of the Power BI report  
├── LICENSE — MIT License  
├── project-logo.png — Project cover  
└── README.md — Project documentation   
  
## Visualization  

![Average Salary in Ukraine](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/images/Average-Salary.png)  

## Example formula  
  
**Table name:** region_tbl  
**Column name with regions:** Region  
**Column name with values ​​for each region:** Value  
  
**The DAX formula for each region would look like this:**  

<code>Kyiv  lbl = 
VAR CurrentRegion = "Kyiv"
VAR CurrentValue = FORMAT(CALCULATE(SUM(region_tbl[Value]), region_tbl[Region] = CurrentRegion), "#,##0")
VAR RegionExists = COUNTROWS(FILTER(region_tbl, region_tbl[Region] = CurrentRegion)) > 0
RETURN
    IF(RegionExists, IF(ISBLANK(CurrentValue) || CurrentValue = "0", CurrentRegion & ": 0", CurrentValue & " ₴ " ), CurrentRegion & ": No Data")</code>
  
 ## Contact  
    
**Name:** [Andrii Isachenko](https://isachenko-andrii.github.io)    
**LinkedIn:** [Andrii Isachenko](https://www.linkedin.com/in/isachenko-andrii/)  
**E-mail:** isao.datastudio@gmail.com   
  
## Acknowledgments    

 - Special thanks to [Nikita Tymoshenko](https://github.com/NickTimosh) for high-quality data analytics [lessons](https://github.com/Youtube-NikitaTymoshenko/PowerBI-UkraineMap/blob/main/README.md) in Ukrainian.
 - Thanks to the [Data Analyst/GoIT](https://goit.global/ua/courses/data-analytics/) course, which was part of this project.

---
  
**Project Status:** Completed.
    
**License:** MIT License.   
