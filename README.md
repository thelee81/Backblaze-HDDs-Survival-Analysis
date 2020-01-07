# BackBlaze Data Center Hard Disk Survival Analysis from Diagnosis Data  
  
<img src="https://www.backblaze.com/blog/wp-content/uploads/2019/08/hard-drive-stats-q2-2019.jpg">  

Since 2013, Backblaze has published statistics and insights based on the hard drives in their data centre. And the HDD diagnosis raw data is available to download for public to use. HDDs consists of enterprise and consumer models and in various capacities.  
Diagnosis was ran every day for all the HDDs and following data are recorded.  
`date`- Date diagnosis executed  
`serial_number` – serial number of the HDD  
`model` – Model number of the HDD  
`capacity_bytes` – Capacity in bytes  
`failure` – Failure flag. failure (1) /no failure(0)  
`smart raw`- All available S.M.A.R.T system monitor values normalised  
`smart normalized`- All available S.M.A.R.T system monitor values normalised  
  
My intention is to analyse what are the HDDs used in 2019 have the good survival rate but along the way will checkout other interesting survival curves. Let’s see what the progress in data storage technology brought to this data centre. This will be a continuously ongoing survival analysis project because the amount of combination can analysed.  
  
Download data at:  
https://www.backblaze.com/b2/hard-drive-test-data.html#downloading-the-raw-hard-drive-test-data  
  
# Kaplan Meier Survival Analysis  
The Kaplan–Meier method is a more sophisticated method of summarising survival data, which uses all the cases in a series, not just those followed up until the selected cut-off. The technique is to divide the follow-up period into a number of small time intervals, determining for each interval the number of cases followed up over that interval and the number of events of interest (e.g. deaths) during each period.  
In this my analysis birth event is the date when the diagnosis data recorded for the first time for the each HDD, death event is when the HDD failure occurs. Censor case is when HDD is removed from the usage before without any failure data recorded. 
