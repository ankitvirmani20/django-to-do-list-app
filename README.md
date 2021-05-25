Inside your newly created python3 venv, create the django project:
django-admin.py startproject toDoListProject

cd toDoListProject

----------------------------------------------------
Activate another instance of the VM and check if the Django server is running:
(You have to run the following command under the venv)

source venv/bin/activate    To activate your virtual environment, in case venv is the name of your created virtual environment

cd toDoListProject
python3 manage.py runserver

----------------------------------------------------

python3 manage.py migrate
(Migrations are related to the database set up in Django)

----------------------------------------------------

set up the seuperuser name and password
python3 manage.py createsuperuser

---------------------------------------------------

Create the application or app in the project folder
python3 manage.py startapp todolistapp

-----------------------------------------------

Add todolistapp application to the list of allowed apps in the settings.py file of the project
nano toDoListProject/settings.py

----------------------------------------------

Create the urls.py file inside the app folder

----------------------------------------------

Go to the project level urls.py file and paset the below:

from django.contrib import admin
from django.urls import path,include
from todolistapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('todolistapp.urls')),
]

----------------------------------------------
