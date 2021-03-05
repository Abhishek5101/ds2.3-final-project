# ds2.3-final-project


### Q1 Deploying a Machine Learning Model to the Web

#### Dockerize a Machine Learning Flask app and deploy it to AWS (Amazon Web Services). 

&rarr;

#### Use the Flask app from the blog article you chose in last week’s (Wed 2/11/2021) class. 


#### a) Submit the link to the blog post with the project you chose to implement (10 pts)
&rarr; [blog post link](https://medium.com/analytics-vidhya/deploy-machine-learning-model-using-flask-to-heroku-beginners-part-1-451b117a4c7e)

#### b) Submit the link to your deployed project from the blog post on AWS. If you were unable to implement the project in the blog post, you can choose to Dockerize the MNIST Digit Recognizer and deploy to AWS instead. (30 pts)
&rarr;

#### Extra Credit For deploying the Flask app from the blog post you chose to Heroku! (submit link) (10 pts)
&rarr; [heroku link](https://diabetes-tutorial.herokuapp.com/)



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

#### List and discuss three ways you could improve the project (15 pts). 
- Make the styling bit more interactive and responsive. Currently the website styling is not reponsive and it takes up unnecessarily long width for all the input parameters as well as the predict button. Some styling would to make it look like a short form would help in the user interaction with the form. We could also do some form input validation in case of an unexpected input from the user. 

- Try to see if it is possible to eliminate any of the many input parameters by fine-tuning the model and looking for correlations. Currently as we visualized in the model, there is a direct positive and direct negative correlation with a lot of the parameters. We could use this to eliminate the number of inputs the user has to enter to make the form shorter. 

- Offer specific medical resources and guidance personlized to each person's. Based on what the model predicts as the result, the user could be redirected to some resources if they are medically unfit and might need to see a medical professional. 

#### Sketch out a rough implementation plan for how you would make these improvements (15 pts).
- To add some styling, we could use the bootstartp CSS library and take advantage for the bootstarp forms which will also handle form validation for us as well as styling. 
- As we saw in the model, heatmap shows strong correlation between a few columns. Insulin is highly correlated with SkinThickness. SkinThickness is also highly correlated with BMI. Age is highly correlated with Pregnancies. This could be used to make some statistical inferences and eliminate some input paramaters from the user. 
- Based on what the model predicts, we could redirect user to an appropriate health or government site should they need a medical guidance. 


