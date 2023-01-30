## google_calendar_integration-_django_rest_api
Google Calendar API OAuth 2.0 for Web Server Applications Integration - Django Rest Framework

Problem: In this assignment you have to implement google calendar integration using django rest api. You need to use the OAuth2 mechanism to get users calendar access. Below are detail of API endpoint and corresponding views which you need to implement.

### prerequisites run this project on a local machine: 

for this you need to Register your application on the Google Developers Console and you need to create Google Account Credentials file(Credentials.json) to implement Google Calendar integration using Django REST API, you will need to use the Google Calendar API and OAuth2 mechanism to authenticate and authorize user access to their calendar.


To register your application on the Google Developers Console and obtain a client ID and secret, you will need to follow these steps:
1. Go to the Google Developers Console (https://console.developers.google.com/).

2. If you already have a project, select it from the project drop-down menu in the top bar. Otherwise, click on the "Select a project" button and create a new project.

3. In the sidebar on the left, navigate to the "Credentials" page.

4. In the "Credentials" page, select the "Create Credentials" button and choose "OAuth client ID" from the options.

5. Select "Web application" as the application type if you are using Django or Flask. if you want to use in .py file or .ipynb then Select "Desktop App" as the application type.

6. In the "Authorized JavaScript Origins" field, enter the base URL of your Django application. This is the URL where your application will be hosted and accessible to users. For example, if your application is hosted on localhost, you would enter "http://localhost:8080".

7. In the "Authorized Redirect URIs" field, enter the URL of the OAuth callback view in your Django application. This is the URL that the user will be redirected to after they have granted access to their calendar on the Google OAuth2 page. For example, if you have a view called "oauth2_callback" in your Django application, you would enter "http://localhost:8080/rest/v1/calendar/redirect".

8. Click "Create" and a client ID and secret will be generated for you. Make sure to save these as they will be used later in your Django application.
Store json file into project directory so it will auto configure path.

Now you have all prerequisites so you can clone this repo and run.
For run this project on a local machine:

1. create virtual env
```
python -m venv django-rest-env
```
2. Activate virtual env
```
source django-rest-env/bin/activate
```
3. go to project directory
```sh
cd google_calendar_integration-_django_rest_api
```
4. Install all python packages required to run this application
```sh
pip install - r requriments.txt
```
5. make sure that Authorized Redirect URIs and REDIRECT_URL would be same in our applicaiton as well as google developer credential file.
6. create database for admin use and for Initializing bydefault table.
``` 
python manage.py makemigrations
python manage.py migrate
```
Hurray !!! All set to run this application in Local
Now run ```  python manage.py runserver 8080 ``` to start local server.
go to 
```
http://127.0.0.1:8080/rest/v1/calendar/init/
```
It will ask for credential of your Gmail account enter that and give required permission you want to give for reading data from calendar.
after this it will redirect it to 
```
http://127.0.0.1:8080/rest/v1/calendar/redirect
```
It will display all data of your calendar using OAuth2 mechanism without getting your private information like gmail password.

So that's it.
