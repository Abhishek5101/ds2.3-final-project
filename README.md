# ds2.3-final-project


### Q1 Deploying a Machine Learning Model to the Web

#### Dockerize a Machine Learning Flask app and deploy it to AWS (Amazon Web Services). 

&rarr;

#### Use the Flask app from the blog article you chose in last week’s (Wed 2/11/2021) class. 

&rarr;

#### a) Submit the link to the blog post with the project you chose to implement (10 pts)
&rarr;

#### b) Submit the link to your deployed project from the blog post on AWS. If you were unable to implement the project in the blog post, you can choose to Dockerize the MNIST Digit Recognizer and deploy to AWS instead. (30 pts)
&rarr;

#### Extra Credit For deploying the Flask app from the blog post you chose to Heroku! (submit link) (10 pts)
&rarr;



### Q2 Deploying a Machine Learning Model to the Web
#### a) What does the app do? (12 pts)
The model predicts the likelihood of a patient having diabetes by measuring several medical predictors.

#### b) What are its major parts and how do they work together?

##### ML model (6 pts)
The machine learning model uses first gathers and cleans the data. The model then proceeds to identify co-relation between features with different data visualization techniques like a heatmap. The model used in this exerices is a logistic regression model which takes target variable y, Outcome, and our independent variables X. 

##### Back end web (6 pts)
Now that the model can make predictions based on certain inputs, the next part it is to structure it into a Flask application that can be served to users. The model is in `model.py` file. On the backend we also use the Pickle library to save the trained model on the disk. As a result when `model.py` is run, the results get generated and stored in `model.pkl` file.
The backend serves two flask routes. The `home()` and `predict()` routes which are used to access the homepage and the results page respectively. 

##### Front end web (6 pts)
The front end uses simple HTML forms with a  bit of styling to 
allow users to input their data which will then be sent to the backend for processing. In Flask we use, Jinja templating library to allow the use of Python variables in HTML files. 

### Q3 Deploying a Machine Learning Model to the Web

#### List and discuss three ways you could improve the project (15 pts)

#### Sketch out a rough implementation plan for how you would make these improvements (15 pts)

