Winter Progress Report
======================

Senior Project 2016

Polymatheia

Django
------

- Two modules: Polymatheia and Components
- Create forms based on the database schema
- Three main components:
  - ``views/``
  - ``urls.py``
  - ``templates/``

The Sitemap
-----------

Designing the sitemap has probably been the hardest part. Here are the 
highlights:

- Index page displaying courses and related assignments
- Course list page with list of assignments for each course
  - Teachers have option to add a new course or update a course here
- Individual course page, w/ list of assignments
  - Teachers can update the course or add an assignment from here
- Individual assignment page, where students can upload/test submissions
  - Teachers can add a test or update the assignment from this page.

Talking to the Database
-----------------------

Right now, only view works, but overall it's pretty simple:

.. code-block:: python

    api_ip = settings.API_IP
    user_data = {'student':['hennign']}
    userobj = requests.get(api_ip+'student/view', json=user_data)
    user = userobj.json()

Up next
-------

Next we'll talk about the Command Line Interface to the system

