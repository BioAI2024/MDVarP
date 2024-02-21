========================================================================
MDVarP version 1.0 2-20-2024

The MDVarP implements an ensemble model based on 1000 random forest predictors 
to identify combinations of modifier variants and disease-causing variants. 

The MDVarP was built under R version 4.0.2.

========================================================================
Executable code:

The executable R script, i.e. MDVarP.r, is in the MDVarP.v1.0/ directory.

==========================================================================
Use MDVarP:
 
Run shell scripts in Windows.

1. Set path
set R_Script= Your Rscript PATH
#eg:   
#set R_Script="C:\Program Files\R\R-4.0.2\bin\RScript.exe"

2. Run MDVarP
%R_Script% MDVarP.r inputfile outputfile

3. One example of command line:
%R_Script% MDVarP.r test_data.txt test_pred.tsv 
