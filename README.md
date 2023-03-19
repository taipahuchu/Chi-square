# Chi-square
ODS PDF FILE="Chisq.pdf";
TITLE "Chisquare analysis of Make as the explanatory variable and Model reponse variable";
FOOTNOTE "Done on %sysfunc(time(),timeampm.)";
data cars;
set sashelp.cars;
IF Invoice >= 25218 then Cost = 1;
ELSE COST = 0;
IF MSRP >= 27560 then Efficiency = 1;
ELSE Efficiency = 0;
PROC FREQ;TABLES Efficiency*COST/Chisq;
RUN;
ODS PDF CLOSE;
