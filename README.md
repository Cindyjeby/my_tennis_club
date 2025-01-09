1. Create a virtual environment
py -m venv <projectname>

2. to activate the environment
source <projectname>/Script/activate

3. then instal Django in the virtual environment
py -m pip install Django

4. while still in the virtual environment navigate to the <projectname> folder to run a project
- then run:
django-admin startproject <djangoprojectname>

5. to run the project server run:
py manage.py runserver
- this should be done at the root folder which in this case will be <djangoprojectname>

6. to create an app run:
py manage.py startapp <nameofapp> for instance (members)
- Note: every time you create an app update in the setting.py to add the app name

7. VIEWS.PY
- Django views are Python functions that take http requests and return http response, like HTML documents.

8. URLS.PY
- are basically files that handle routing from page to page
in this case example check:
my_tennis_club/members/urls.py and my_tennis_club/my_tennis_club/urls.py
then run server and search: 127.0.0.1:8000/members/ (members being the path to the new page)

9. TEMPLATES folder
- handles all html files

10. Django Models
- A model is a table in your database.
- after adding what you want to be in the table to the model.py file you run this command:
 - py manage.py makemigrations <nameofapp>(members: which is the name of the app we created)
 this creates a migrations folder that describes the changes and stores it here.
- the table is still not created,to create a database run this command:
 - py manage.py migrate
- if you want to view the SQL statements that weere executed from migration run this:
 - py manage.py sqlmigrate <nameofapp: members> 0001
