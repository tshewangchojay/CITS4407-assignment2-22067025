# CITS4407-assignment2-22067025
Bash Shell Script-Data Cleaning and Analysis of US Cybersecurity Breaches


This assignment will involve creating two Bash Shell scripts, which will use Unix tools, e.g. Sed, Awk, and/or calls to other Bash Shell scripts. The top level scripts are to be called preprocess and breaches_per_month.
This assignment will make use of the Catalogue of US Cybersecurity Breaches data. There are two parts to this assignment. 
- The first will involve data-cleaning, which is a hugely important first step in almost every data analysis task. 
- In the second part you will use cleaned data to analyse the distribution of incidents across months.


Data Cleaning
The Bash Shell script at the front of the data-cleaning task must be called preprocess, and will be given the name of a data-file as its only argument. The primary data-file you will be using is Cyber_Security_Breaches_noym.tsv, though other data-files will also be tested. You can assume the interpretation of the fields will not vary.
preprocess needs to achieve the following aims:

Perform the usual anti-bugging/sanity-checking of the fields, particularly those which are structured, i.e. not free text.
Add a month column (containing numbers 1..12) and a year field (containing 4-digit years), in that order, after the final column (currently Type_of_Breach). The data for these should be taken from the fourth (Date_of_Breach) column of the input data-file, and if there is a range of dates – indicated by a pair of dates separated by a hyphen – please use the first of these (the start date). Please bear in in mind that this is US data, so therefore uses the US date format: Month/Day/Year.
The Type of Breach column has the primary breach-type, sometimes followed by alternative interpretations, separated from the primary breach by a comma or slash "/". To make the breach-type more uniform remove everything in field after the first comma or slash.
The Location of Breached Information and the Summary columns can be dropped.
Any rows with erroneous data should be dropped.
New: The output of preprocess should be sent to standard output.


Data Analysis
The particular analysis you are asked to do for this assignment is to see if there is a pattern to the breaches across months, for the several years that are covered by the data-file. The Bash Shell script at the head of this program must be called breaches_per_month; it too takes a single argument: the name of the (cleaned!) data-file. The program should compute the total number of incidents per month for each of the months, and then compute the median and median absolute deviation (MAD) across the 12 months. (Median and MAD are more robust measure of centrality and spread than mean and standard-deviation when you cannot be sure that the data is normally distributed.)

The values for the median and MAD should be printed to standard output. When you have the median and MAD, you are to print a table of the months, where, against each month you list the number of incidents and then either "++", if the count is 1 median-absolute-deviation above the median (or more); "--", if the count is 1 median-absolute-deviation below the median (or less). If the count is within 1 median-absolute-deviation of the median don't add anything.
