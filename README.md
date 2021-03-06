Deployment of Deep learning model on web interface using python Flask and Heroku.

I have trained and saved the model(word_embedding_self2.h5) as part of separate pipeline, also saved word tokenizer(tokenizer1.pkl) created by using keras tokenizer which will latter be used while doing prediction.

Saved model and tokenizer are used in app.py file and this file is deployable.

Now we need to create templates folder which will have HTML file index.html. The flask framework has been written in a way so that it looks for HTML template files in a folder that should be named templates. So, you should create such an empty folder and then put all the HTML templates in there. HTML is a markup language used to render webpages and it is used to interact with application so pass user input and show the output/result passed back by application.

I used flask in app.py file. it reads the HTML template and returns it to the webpage. we imported the render_template method from the flask framework and then we passed an HTML file to that method. The method will generate a jinja2 template object out of that HTML and return it to the browser when the user visits associated URL.

We can use the above points(1-5) to deploy our model locally by running "python app.py" in command prompt which creates a link and that link can be used on web browser : http://127.0.0.1:5000/predict. Deploying the model globally please follow points 7 till end. I have used Heroku for the same.

Next we need to create requirements.txt which includes all the libraries with version number used in the model so that Heroku can install these for the deployment. We can use "pip freeze > requirements.txt" to populate the file.

Create procfile without any file extension. It specifies the commands that are executed by the app on startup.

if model used NLTK, create nltk.txt file and include the corpora name, so that Heroku install them.

Create profile in Heroku, click on New(right corner) and select create new app. Fill the app name and upload all the files using Github and deploy it. Heroku will create an URL which can be used globally on web browsers.
