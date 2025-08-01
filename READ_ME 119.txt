A Data-Driven Approach to Autism Prediction

Summary:

Autism is a kind of developmental challenge that makes it hard for people to socialize, communicate, and behave like others.
Even though you can't tell just by looking, people with autism may do things differently.
Some might be really good at thinking and learning, while others might find these things more difficult. 
Some need lots of help every day, while others don't need as much.

Goal :

In this contest, we have data from surveys people filled out on a mobile app. 
The goal is to use this data to predict if someone might have autism based on certain information.
The way we measure how well these predictions work is through something called the AUC-ROC score.

Autism used to be divided into different types, like autistic disorder, PDD-NOS, and Asperger syndrome. 
Now, all these are just called autism spectrum disorder.

By using machines to understand this data, we're trying to make it easier to tell if someone might have autism. 
The competition is like a game where people build computer programs to make these predictions. 
The better the program is at telling who might have autism, the higher the score. 
This way, we hope to learn more about autism and help people who have it.

first think to do :

Before we start project make sure you have jupyternote book https://jupyter.org/install in your computer or pc

Also make sure you follow this steps install libaries to python :

Step 1 : open commend promt in your pc or laptop 
Step 2: type pip ...follow all...install
Step 3 : just copy past in commend promt

pip install confusion_matrix
pip install metrics
pip matplotlib install
pip numpy install
pip pands install
pip seaborn install
pip  plotly install
pip sklearn install
pip stats install
pip stats install
pip stats install

Step 4: open juyternote book file .py in jupyternotebook .
Step 5: uplode database or dataset in jupyter lib in right corner gave uplode and select dataset and gave upload .
Step 6 : run one by one in order dont run in bunch and wait for output and move on 

If any unsolved error please be mail error we will quickely solve that.

CODE EXPLAIN IN STEPS READ EVERY LINES AND UNDERSTAND PROJECT WELL ...

We going do project in different part steps: 

TOTAL 32 LINES PYTHON CODE EACH LINE EXPLAINED WELL READ IT:

IN LINE [1] : install and import  libraries mainly 

Path for project:  PATH = 'Autism-prediction'.
Train dataset: train = pd.read_csv("train.csv") 
code set up paths and read data from CSV files

IN LINE [2-3] :Look at the head of the test display data cvc data and list table head lines.

IN LINE [4]  : Null values from dataset .No null values in both train and test datasets proven.

IN LINE [5-6] : data cleaning process

In dataset like fix the spelling issue,unwanted values, capitalization,
and function,drop un-important cols and equations removed for better results and reduce run time.

IN LINE [7-8] : Check for categorical features uniqueness 

1. Only country of residence columns has different unique values in train (61) and test (44) datasets.
2. Watch this feature if label encoding is reruired in model training.

IN LINE [9] : Features distribution Graph show clear positive and negative ASD.

Target : ASD Class 

1. round 77% of the target is ASD negative (0) and 23% ASD positive (1)
2. Target class is imbalanced.

IN LINE [10] : Gender Male and Female patient ASD positive and negative result in graph

1.Gender distribution is fairly balanced. 52% are Females (f) and the remaining 48% are males (m)
2.63% of ASD_positive are females.

IN LINE [11] : Ethnicity: Ethnic group of the patient in various countries graph representation.

1. 11 ethnic categories are present in the data, including "?" (not willing to tell?/is it NA?) and others
2. The majorities are White-European followed by the "?", Asian and Middle-Easters
3. Among the ASD-positive subjects, White-European make up 58% while being only 26% of the total sample (train dataset).
4. Asian (9%) and Latinos & "?" (both at 8%) come in second and third.


IN LINE [12] : Jaundice :Whether the patient had jaundice at the time of birth or not .

1.The majority of the patients had no jaundice at birth
Of those who had jaundice at birth, the majority (123) had tested ASD_negative compared to the 73 positive cases. 
2.Jaundice at birth may not mean ASD positivity.

IN LINE [13] : Autism in the family : Whether an immediate family member has been diagnosed with autism or not .

1. Most patients have no immediate family who have been diagnose for autism.
However, those who have autistic family members are likely to be diagnose with autism.
2. 72 out of 117 (i.e 62%) of the ASD_positive patients have family members with autism.

IN LINE [14] : Country of Residence of the patient 

1. USA has the most patients in the dataset (train), UEA and New Zealand come in second and third.
2. Only USA had equal amount of patients in both target groups (ASD_positive and ASD_negative)

IN LINE [15] :  Previous screening test Whether the patient has undergone a screening test before or not.

1. Only 35 patients out of 800 have undergone previous screening tests.
2. 7 of the 35 patients have tested ASD_positive.

IN LINE [16] :Relation of patient who completed the test 

Most patients have done the tests themselves. health care professional comes last.

IN LINE [17] : Age Distribution : Young patients

1. ASD_positive:
average age is 32; the min is 10.9 years; and the maximum is 71.1 years

2. ASD_negative
average age is 27.6; the min is 9.6 years; and the maximum is 72.4 years


IN LINE [18] : Screening Test scores (QA1-10)

1. The QA test scores looks binary (they are either 1 or 0).
2. Most of the questions except A8_score and (slightly) A1_scores.
3. Most of the screening question have fairly separated the positive and negative cases.

IN LINE [19] : Screening Test Result  distribution

1. The screening test scores results are for the ASD_negative cases seems normally distrubuted with a mean value of around 6.
2. Whereas for distribution of the ASD_positive casea are left-skewed with mean value of 10.5.
3. Higher QA test score means higher chances of being ASD_positive.

IN LINE [20 -21] :  Correlation heatmap (numerical features)

1. From the numerical features only result shows moderate correlation with target Class/ASD
2. We use Cramer's V correlation coefficient.
3. We see that A3_Score, A6_Score, A9_Score and ethnicity are moderately correlated with the target (Class/ASD).
4. We also notice that A1_Score and A8_Score have weak correlation with the target.
5. Previous participation in screening programme (used_app_before) has no correlation with any other features or target.


Short conclusion (EDA):

Target is imbalanced.
One feature (country of residence) has different uniques values in train and test dataset.
Having Jaudice at birth seem to have no major influence on autism. However, family history seem to have correlation with autism diagnose.

MODELING STEP: IMPORTANT PART

1. Logistic regression
2. Random forest
3.ExtraTreesClassifier
4. linear model

IN LINE [22 -25] : PROCESSING MODELS :  Build simple models such Logistic regression, Random forest, etc
Try Stacking, Voting classifiers

IN LINE [26] : Logistic regression model And output table.

IN LINE [27] : ROC_AUC curve Logistic regression graph

IN LINE [28] : Submission (LR) 

IN LINE [29] :ExtraTreeClassifier  And output table.

IN LINE [30 -31] :Extra trees classifier: ROC_AUC curve graph.

IN LINE [32] : Blended submission 

See V6 for Stacking classifiers + Voting classifiers

LB scores were worse than the LR (0.93939)























































































