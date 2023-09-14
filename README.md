# Hotel Management System

* Requirement Analysis Document - System Design Document - Object Design Document - Mockups - Class Diagram - ER Diagram are in the "Documents" Folder.
* It is hotel management system which has 5 different user types: `<br>`
  Admin - Manager - Receptionist - Staff - Guest  (Each of the types have different permission and functionality.)
* There are some screenshots of the program on "Screenshots" folder.

### In order to download and run the project ( It is assumed that Python 3 is already installed ):

1. Install Django and Apps:

```shell
pip install Django
pip install django-phonenumber-field
pip install phonenumbers
```

## Needed to create roles and admin account to add new employee accounts

2. Change Directory to Django---Hotel-Management-System/HMS and start the Shell:

```shell
python manage.py shell
```

* Then execute these, one by one:

```shell
from django.contrib.auth.models import Group, User
```

```shell
from accounts.models import Employee
```

```shell
Group.objects.create(name='admin')
```

```shell
Group.objects.create(name='manager')
```

```shell
Group.objects.create(name='receptionist')
```

```shell
Group.objects.create(name='staff')
```

```shell
Group.objects.create(name='guest')
```

```shell
user = User.createuser=User.objects.create_user('admin', password='admin123', email='admin@email.com')
```

```shell
group = Group.objects.get(name="admin")
```

```shell
user.groups.add(group)
```

```shell
admin = Employee(user=user, salary=0)
```

```shell
admin.save()
```

### Finally:

* Exit the shell and set the database:

```shell
python manage.py makemigrations
python manage.py migrate
```

Then, start the surver

```shell
python manage.py runserver
```

* This will work if correctly set up.

## Notes:

#### Note 1: You can only sign up as a guest to the system. In order to add employee (Manager - Receptionist - Staff):

* Login in to the system with username: "admin" and password : "admin123"
* Go the employee page on options in navbar.
* Click "Add New Employee" button, fill the form and send it.
* You will see the success message. Then, you can use that employee to enter the system
