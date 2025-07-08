# NCRB-Crime-Against-Women-analysis-and-Forecasting
We have **NCRB IPC** from 2017-2022 to detect Crime hotspots and do state and district wise analysis on **Crime against women**. Among the crimes mentioned in the data we have considered the following as crime against women:
1. Dowery Deaths
2. Rape cases
3. Attempted Rape cases
4. Buying and selling of minor girls.
5. Trafficking of forign girls for prostitution.
6. Assault on women.

We have used **Google's BigQuery for conducting manual Analysis and LLama-3.7B for automating theanalysis process and finding the insights.**

Following SQL commands were used for analysis of data. (There were various other analysis too. But we have included only the final and selected ones to keep the README short):

SELECT state_name,district_name, crime_type, SUM(cases) AS total_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
GROUP BY state_name, crime_type, district_name
ORDER BY total_cases DESC

SELECT DISTINCT crime_type 
FROM `sql-project-464805.CrimeData.crime_ipc_int`
ORDER BY crime_type;

SELECT 
  state_name,
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE crime_type = 'rape' OR crime_type = 'dowry_deaths' OR crime_type = 'assault_on_women' OR crime_type = 'proc_minor_girls' OR crime_type = 'import_girls_frgn_cntry' OR crime_type = 'sell_minors_prost' OR crime_type = 'buy_minors_prost' OR crime_type = 'atmpt_rape' 
GROUP BY state_name
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name,
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE crime_type = 'rape' OR crime_type = 'dowry_deaths' OR crime_type = 'assault_on_women' OR crime_type = 'proc_minor_girls' OR crime_type = 'import_girls_frgn_cntry' OR crime_type = 'sell_minors_prost' OR crime_type = 'buy_minors_prost' OR crime_type = 'atmpt_rape' 
GROUP BY state_name, district_name,
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2017, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2018, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2019, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2020, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;

SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2021, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;


SELECT 
  state_name, district_name, year
  SUM(cases) AS total_rape_cases
FROM `sql-project-464805.CrimeData.crime_ipc_int`
WHERE year= 2022, crime_type IN ( 'rape', 'dowry_deaths', 'assault_on_women', 'proc_minor_girls',  'import_girls_frgn_cntry',  'sell_minors_prost',  'buy_minors_prost',  'atmpt_rape' )
GROUP BY state_name, district_name, year,
ORDER BY total_rape_cases DESC
LIMIT 5;




