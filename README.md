#  ML Disaster-Response-Pipeline
**Table of Content**

<ol>
<li>Project Motivation</li>
<li>File Description</li>
<li>Instruction</li>
<li>Licensing, Authors, Acknowledgements</li>
</ol>

# Projection Motivation
Response to a accident scene or crime scene are often times delayed inadvertently because of human error or the unvoidable latency that occur when information is being shared between persons.This is ubiqitous among emergency reponse agency in the event to responding to distress calls. As  such to solve this problem, I have created a ML model that is able classify distress messages according to the correct response agencies.
# File Description
A jupiter notebook with an ETL model was provided. The data set in the form of csv files were extracted fron Figure Eight and merged into one file, then load into  a sql database. This data was then transformed using the fillowing text process steps:

<ol>
<li>Cleaning to remove irrelevant items,such as HTML</li>
<li>Normalize by converting all text to lowercase format and removing punctuation</li>
<li>Split text into sequence of words or token</li>
<li>Remove words that are common ,also known as stop words</li>
 <li>Converting words into their dictionary form or root ,using lemmatizaton</li>
</ol>

After cleaning the data  four pipeline contructs were made which contain a list of transformers and estimator pairs that defined a sequence of steps.
The countvectorizer  and Tfidf were specifically for feature extraction, hence preparing the data for the ML alogorthms. Four different classifiers incuding: Kneighbor classifier and Random Forest classifier were  used as estimators.  

The best models was selected then  save as a pickle after performing tunning model tunning with grid search.
# Instructions

Run the following commands in the project's root directory to set up your database and model 

 <ol>
 <li>To run ETL pipeline that cleans data and stores in database </li>
 <li>python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db </li>


 To run ML pipeline that trains classifier and saves
 <li>python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl</li>
 </ol>
 Run the following command in the app's directory to run your web app.
     python run.py

Go to http://0.0.0.0:3001/   
   # Licensing, Authors, Acknowledgements
The templates used in this project was provided Udacity and the was provided by Figure Eight.
