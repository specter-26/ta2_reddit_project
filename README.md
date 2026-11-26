# ta2_reddit_project

## Project Description
This project uses NLP to analyze 4 subreddits from Reddit:
* relationship_advice
* relationshipadvice
* dating_advice
* datingadvice

The primary goal is to create a predictive model which will predict the what categories a particular relationship issue falls under for Reddit posts, and to predict what kind of advice would most likely be offered. 

Additional unsupervised analysis and descriptive statistics were also performed to evaluate common patterns within these types of subreddits. 


## Folders:

### data/sample:
Here can be found anonymized (hashed) sample of reddit posts and comments, along with the human and AI labelled annotations. 
 
_comments_sample_anon.csv:_
CSV of Reddit comments across the four subreddits, along with annotations about what kind of advice was given to the original post. 

_posts_sample_anon.csv:_
CSV of Reddit posts across the four subreddits, along with annotations about what the type of relationship topic (i.e. conflicts, trust, cheating, etc) and annotations on what type of a relationship it is (i.e. dating, family, friends, etc).

### notebooks:
_01_data_collection_and_prep.ipynb:_
All of the initial data cleaning, preparation, anonymization, and exploratory data analysis. 

_02_Data_Annotation.ipynb:_
The cleaning used for standardizing the data annotations and making them nice and clean for the modelers to work with. \
(More about annotations below)

_03_data_modelling.ipynb:_
Create the baseline comparison models using TF-IDF and Logistic Regression. 

_04_improved_models.ipynb:_
Create the transformer models and explored unsupervised approaches. 

_05_advice_across_situations.ipynb:_
Compare Reddit advice across relationship situations using thread-level statistics and qualitative examples.

## About Annotations 

Both files contain 5 common columns: ‘Primary Labels’ and ‘Secondary Labels,’ ‘Notes,’ ‘Annotator.’
* Primary Labels: Always marked. Some type of main premise of the post or comment (more details below).
* Secondary Labels: Sometimes marked but often null. A label that the post/comment may also fit into
* Notes: Any additional notes given. This is more so for the annotator (Nick) so it can be ignored. 
* Annotator: ‘Human labeled’ (manually labeled by me, including changes I made to AI labels), ‘AI - Human verified’ (AI was uncertain about these labels, so I verified them), ‘AI - Not verified’ (AI was certain about these labels).

<br>


comments_sample_anon.csv contains two more columns: ‘isResolved?’ and ‘Relationship_type.’
* isResolved?: 1 if the post’s situation is resolved (i.e. got help/therapy, broke-up and no contact, etc. Often [UPDATE] posts). 0 if not (most common).
* Relationship_type: Family, Friends, Dating, Married, Coworkers, Other. 
Note: ‘dating’ includes engaged/fiancés, situationships, hook-ups, and crushes.

<br>

### Primary & Secondary Labels
_Post Labels_
* Early Dating: Advice on crushes or dealing with early stage problems (less than 6 months dating). Situationships are included here. 
* Breakups: Advice on how to breakup, breakup aftermath, or highly considering breaking up. 
* Reconciliation: Moving on from a conflict and changing things (being sorry and fixing the issue). 
* Communication: Issues primarily stemming from being unable to communicate properly or having communication mismatch.
* Conflict: Fights between people. 
* Boundaries: Person crossing personal boundaries or doing things unacceptable with friends (i.e. cuddling friend is platonic to one, but cheating to another). 
* Trust: Being unable to trust what someone says or what they do when away.
* Cheating: Cheating. 
* Uncertainty: Uncertain about what the future might hold and processing how to move on with this. 
* Sex/Intimacy: Sexual activity or other physical closeness (i.e. kisses/making out, cuddling)
* Other: Can not be properly categorized as one of the above. 
<br>

_Comment Labels_

* Talk it through: Discuss and communicate with the person.
* Set boundary: Set and enforce a boundary of some sort. Whether that be physical, emotional, how much they can talk to you, what they can do, who they can talk to, etc. 
* Repair/Help: Work through it together, apologize, see therapy, etc. 
* Wait/More info: Either wait to see what happens or what someone will do, or the commenter is asking a question to get more info. 
* Leave/Disengage: Break up, block, ghost, etc. 
* Dating Strategy: Advice on getting a partner. 
* Other: Advice that is clear but does not fit in any above category.
* No advice: Commenter is sarcastic, rude, or otherwise unhelpful. 

### AI Prompt (ChatGPT 6.2 Sol Light)
Here is an excel file with my annotations for various dating and relationship subreddits. Based on my already human-made annotations, create your own for the entire spreadsheet. Check a dropdown box to say that you are uncertain and I need to review. Also create a dropdown box for you to check in case your labels are different from mine. 
Here are the labels that I need you to use:\
_Insert post or comment labels_








