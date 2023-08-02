# Empathy_Classification_PBC4cip

A repository for classification experiments regarding the use of PBC4cip for empathy classification using the EmpatheticConversations(EC) database

In this repository, there is the necessary code and databases to replicate the work regarding classifgication of the paper: "An Explainable Artificial Intelligence Approach for Detecting Empathy in Textual Communication" 
(https://doi.org/10.3390/app12199407) 

From the EmpatheticConversations database, we provide the steps to replicate the work as follows: 

1. Use the EmpatheticConversations.xlsx file in addition to the Main_Representation_Preparation code to prepare the database into a form that separates the individual features.
   Each data point represents a text utterance comprised of the following features:
   https://pub.mdpi-res.com/applsci/applsci-12-09407/article_deploy/html/images/applsci-12-09407-g005.png?1663830566
3. Separate the data into five folds using the Waikato Environment for Knowledge Analysis (WEKA): https://www.cs.waikato.ac.nz/ml/weka
   We have decided to provide our own folds, they can be found in the "Folds" folder.
   The folds must be separated into training and testing data using the following format:
  *   Empathyabase-'+(number of fold)+'tra.csv  for the training set
  *   Empathyabase-'+(number of fold)+'tst.csv  for the test set
   We provide the .arff and .csv files for each of our folds.
3. Carry out classification.
   It is possible to carry out classification accross all folds and obtain the following average metrics for each classifier:
    * Accuracy
    * Recall
    * AUC
    * Precision
      
  Nevertheless, we also provide the code for carrying out classification tests for each of the folds, in which we can also obtain confusion matrices.
  We used these confusion matrices to calculate the Closeness Evaluation Measure [1] in an attached excel file for each Fold.

  We recommend carrying out the classification task of PBC4cip per Fold using the WEKA implementation of the classifier, as found in Dr. Octavio Loyola-González website: https://octavioloyola.info/papers/PBC4cip/index.html
  For this, use the .arff folds found in this repository. This is because the Python implementation found in this code can take some time to run. 

#Individual utterance empathy testing

  We have included a folder that allows a user to individually test the empathy levels present in a single utterance. The steps to carry out this task is as follows: 

  1. Train the PBC4cip classifier using the jupyter notebook "Full_database_PBC4cip_training" file.

      We provide our own already trained classifier in the repository with the name: trained_pbc4cip.sav. If you wish to use it you may skip this step. 
   
  2. Run the jupyter notebook file "testing_trained_pbc4cip".
      You will be presented with a prompt and you might answer with the utterance you feel appropriate, the classifier will predict the levels of empathy in your utterance. 
      NOTE: This will require that you run individually the steps to carry out the database processing. We provide access to our own license of paralleldots as an example in the code. You might need to run the paralleldots data retrieval sections multiple times until no errors are found. Please use your own paralleldots license. The license in the repository is not for commercial uses.
  3. You will obtain a predicted value for the levels of empathy in your utterance.  


  This work was developed as the Master's thesis work of Mr. Edwin Carlos Montiel Vázquez at Instituto Tecnológico y de Estudios Superiores de Monterrey, Estado de México Campus. 
  The credit for this thesis work goes: 

  Author: Edwin Carlos Montiel Vázquez

  Advisor: Dr. Jorge Adolfo Ramírez Uresti

  Co-Advisor: Dr. Octavio Loyola González 

   [1] Enrique Amigo, Julio Gonzalo, Stefano Mizzaro, and Jorge Carrillo-de-Albornoz. 2020. An Effectiveness Metric for Ordinal Classification: Formal Properties and Experimental Results. In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics, pages 3938–3949, Online. Association for Computational Linguistics.

# License
   Please refer to the license file in the repository for information of the license.
