# Supplementary Material - Machine Learning for Change-Prone Class Prediction: A History-Based Approach

On the use of Change History Data to Enhance Class
Change-Proneness Prediction Models

## Abstract

As software evolves, new artifacts are created, modified or removed. One of these main
artifacts generated in the development of object-oriented software is the class. Classes
have a very dynamic life cycle what may result in additional costs to the project.
One way to mitigate this is to detect, in the early stages of the development, classes
that are prone to change. To predict the change proneness of a class, approaches
in the literature adopt Machine Learning (ML) algorithms. The problem with most
of these approaches is that they do not consider the temporal dependency between
training instances, that is, they consider the instances are independent. To overcome
this limitation, this work presents an approach for predicting change proneness based
on the class change history. The approach uses the sliding window method and is
evaluated to obtain six kinds of models, which are derived by using different set of
metrics as predictors: structural, evolutionary, and smell-based. The evaluation uses
five systems and four ML algorithms, and also explores some resample techniques
to deal with imbalanced data. Independently of the kind of model analysed and
algorithm used, our approach overcomes the traditional one. The approach produces
the best results or equivalent ones in 399 cases (83.13%) consideringa all systems, kinds
of models, indicators and algorithms. In general, models that consider evolutionary
metrics present the best performance. Adding smell-related information in the feature
set does not impact the performance. Random Forest with the resample technique


## Folders

- Datasets: Contains the datasets used in the project, and the correlation, confusion matriz e distribution of the datasets
- Metrics definition: Contains the definition of all metrics related to the project results generated by the scripts
- Results: Contains complementary charts and tables for each research question
- Scrips: Contains scripts to statistical analysis, to extract metrics and to run tradicional and history based approach




## Scripts
Each script starts with "main_" and is responsible for some individual part of the process.

- main_organic: read json generated by organic and covert to csv  
- main_evolutiveMetricsExtractor: extract evolutive metrics from repository  
- main_changeDistillerWrapper: execute changedistiller to extract code changes  
- main_historyBasedApproach:  run history-based approach   
- main_tradicionalApproach: run tradicional approach  
- main_joinMetrics: join metrics of organic, understand, ck, evolutional and changeDistiller  
- main_chats: Generate charts related to the models
- main_count_resample_techniques: Run the resample techniques analysis
- main_information_gain: Run the information gain analysis
- main_raking_window_size: Generate ranking of the window size
- * Some paths and names may be required to run the scripts *



## Extras

To run the script: python3 main__changeDistillerWrapper.py --pathA --pathB --commits --projectName --absolutePath --mode  

--pathA - path of the project to checkout --pathB - secodary path of the project (each path will be checked out via git) --commits - csv file of commits to be compared (commitA,commitB) --projectName - name of the project --absolutePath - absolute path of the main folder of the script --mode - if tag, the script will compare all commits with tag and ignore the csv file 

Example: 

python3 changeDistiller.py --pathA "/mnt/sda4/projects-smells/results/changeDistiller/projectA/jgit/" --pathB "/mnt/sda4/projects-smells/results/changeDistiller/projectB/jgit/" --commits commits.txt --projectName "jgit" --absolutePath "/mnt/sda4/projects-smells/results/changeDistiller/" --mode "tag" 
