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

11. Django Insert Data
To Add Records
- we will use python interpreter(python shell)
- Run: py manage.py shell
- then: from members.models import Member
- then: Member.objects.all()
- then you will get: <QuerySet []>
QUERYSET: this is a collection of data from a database.
- then to add data you run: member = Member(firstname='', lastname='')
- then save: member.save()
- then to check if it saved run: Member.objects.all().values()

TO Add Multiple Records
- member1 = Member(firstname='', lastname='')
- member2 = Member(firstname='', lastname='')
- member3 = Member(firstname='', lastname='s')
- member4 = Member(firstname='', lastname='')
- member5 = Member(firstname='', lastname='')
- members_list = [member1, member2, member3, member4, member5]
- for x in members_list:
-   x.save()

12. Django Update Data
- still in the shell we run the following comands: 
  -  from members.models import Member ; this show all records
  - x = Member.objects.all()[5] ; ill be changing the laste name in the file.
  - x.firstname ; shows the name of the person's index you chose
  - then save: x.save()
  - then check if updated: Member.objects.all().values()

13. Django Delete Records
- still working in shell
first you get the records:
   - from members.models import Member
then select a member:
   - x = Member.objects.all()[2]
then confirm the name:
   - x.firstname
if its the one delete:
   - x.delete()
to check:
   - Member.objects.all().values()

14. Django Update Model
- To add a field to a table after it is created, open the models.py file, and make your changes.
- Then make a migration:
    - py manage.py makemigrations members
    - py manage.py migrate - to create it on the table
- then insert data:
    - run: py manage.py shell - to start shell
    - run: from members.models import Member
    - run: x = Member.objects.all()[0]
    - run: x.phone = 5551234
    - run: x.joined_date = '2022-01-05'
    - run: x.save()
    - run to check: Member.objects.all().values()

15. Testing in Django
- here we have created a template in template called template.html which can be used to test how a file would look without tamplering with the main project, this is very optional.