"# PhenoModifierRF_V1" 

#run the following 2 steps to use PhenoModifierRF to predict associated-pair 

set R_Script="C:\Program Files\R\R-4.3.2\bin\RScript.exe"  # 1. set RScript path
%R_Script% RF_predict.r inputfile outputfile               # 2. run PhenoModifierRF to predict,  you need to define 2 fiels: inputfile which contains the informaiton of variant pairs (format like example);outputfile for prediction results 

# for example: 
%R_Script% RF_predict.r data\test_data.txt  data\test_pred.tsv  #output includes 3 columns:"C-score","S-score","Associated-pair_predicition"
