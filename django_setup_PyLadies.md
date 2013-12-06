###Django unchained - a PyLadies story

In the early days, Web developers wrote every page by hand. Updating a Web site meant editing HTML; a “redesign” involved redoing every single page, one at a time.  
As Web sites grew and became more ambitious, it quickly became obvious that that situation was tedious, time-consuming, and ultimately untenable. PHP fixed many of these problems, and it took the world by storm – it’s now by far the most popular tool used to create dynamic Web sites, and dozens of similar languages and environments (ASP, JSP, etc.) followed PHP’s design closely. PHP’s major innovation is its ease of use: PHP code is simply embedded into plain HTML; the learning curve for someone who already knows HTML is extremely shallow.  
But PHP has its own problems; its very ease of use encourages sloppy, repetitive, ill-conceived code. Worse, PHP does little to protect programmers from security vulnerabilities, and thus many PHP developers found themselves learning about security only once it was too late.  
These and similar frustrations led directly to the development of the current crop of “third-generation” Web development frameworks. These frameworks – Django and Ruby on Rails appear to be the most popular these days – recognize that the Web’s importance has escalated of late. With this new explosion of Web development comes yet another increase in ambition; Web developers are expected to do more and more every day.  
Django was invented to meet these new ambitions. Django lets you build deep, dynamic, interesting sites in an extremely short time. Django is designed to let you focus on the fun, interesting parts of your job while easing the pain of the repetitive bits.  

####Installing Django
If you’re on Linux or Mac OS X, you probably have Python already installed. Type ```python``` at a command prompt (or in your terminal, on OS X). If you see something like this, then Python is installed:  
<pre>
Python 2.7.3rc2 (default, Apr 22 2012, 22:30:17)  
[GCC 4.6.3] on linux2  
Type "help", "copyright", "credits" or "license" for more information.  
</pre>

Otherwise, you’ll need to download and install Python. It’s fast and easy, and detailed instructions are available at http://www.python.org/download/  
Official releases have a version number, such as 1.4.2, 1.4.1 or 1.4, and the latest one is always available at http://www.djangoproject.com/download/  

We installed the so-called [development version](https://docs.djangoproject.com/en/dev/topics/install/#installing-development-version), as it's the most up-to-date version of Django and we like living on the (bleeding) edge:  

1. Make sure that you have ```Git``` installed and that you can run its commands from a shell. (Enter ```git help``` at a shell prompt to test this.)   

2. Check out Django’s main development branch (the ‘trunk’ or ‘master’) like so:  

``` git clone git://github.com/django/django.git django-trunk```  

This will create a directory django-trunk in your current directory.  

3. Make sure that the Python interpreter can load Django’s code. The most convenient way to do this is via pip. Run the following command:  

``` sudo pip install -e django-trunk/ ```

(If using a virtualenv you can omit ```sudo```.)

This will make Django’s code importable, and will also make the django-admin.py utility command available. In other words, you’re all set!

For some post-installation positive feedback, take a moment to test whether the installation worked. In a command shell, change into another directory (e.g., not the directory that contains the django directory) and start the Python interactive interpreter by typing ```python```. If the installation was successful, you should be able to import the module django:  
<pre>
import django  
django.VERSION  
(1, 4, 2, 'final', 0)  
</pre>

####Start your new project
If this is your first time using Django, you’ll have to take care of some initial setup. Namely, you’ll need to auto-generate some code that establishes a Django project – a collection of settings for an instance of Django, including database configuration, Django-specific options and application-specific settings.  
From the command line, ```cd``` into a directory where you’d like to store your code, then run the following command:  
```django-admin.py startproject mysite```

Let’s look at what startproject created:  
<pre>
mysite/  
    manage.py  
    mysite/  
        __init__.py  
        settings.py  
        urls.py  
        wsgi.py  
</pre>

These files are:  
- The outer mysite/ root directory is just a container for your project. Its name doesn’t matter to Django; you can rename it to anything you like.  
- manage.py: A command-line utility that lets you interact with this Django project in various ways. You can read all the details about manage.py in django-admin.py and manage.py.  
- The inner mysite/ directory is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g. mysite.urls).  
- mysite/__init__.py: An empty file that tells Python that this directory should be considered a Python package. (Read more about packages in the official Python docs if you’re a Python beginner.)  
- mysite/settings.py: Settings/configuration for this Django project. Django settings will tell you all about how settings work.  
- mysite/urls.py: The URL declarations for this Django project; a “table of contents” of your Django-powered site. You can read more about URLs in URL dispatcher.  
- mysite/wsgi.py: An entry-point for WSGI-compatible web servers to serve your project. See How to deploy with WSGI for more details.  

Let’s verify this worked. Change into the outer mysite directory, if you haven’t already, and run the command ```python manage.py runserver```. You’ll see the following output on the command line:  
<pre>
Validating models...  

0 errors found  
December 05, 2013 - 15:50:53  
Django version 1.7, using settings 'mysite.settings'  
Starting development server at http://127.0.0.1:8000/  
Quit the server with CONTROL-C.  
</pre>

You’ve started the Django development server. It's with Django so you can develop things rapidly, without having to deal with configuring a production server until you’re ready to show your web application to the world.
Now that the server’s running, visit http://127.0.0.1:8000/ with your web browser. You’ll see a “Welcome to Django” page. It worked!  

####Git it?!
We'll add version control to your allll new web application, to keep track of the progress (and changes) we're about to make. Need more info on Git? Persuade Laura to give a lightning talk on the subject!  

Check if Git is installed by typing ```git --version``` (1.8 or higher preferred) in the terminal.  

If not, [download Git here](http://git-scm.com/downloads). Then, setup your local Git profile - In the terminal:  
- Type ```git config --global user.name "your-name"```  
- Type ```git config --global user.email "your-email"```
- To check if Git is already config-ed you can type ```git config --list```  

Create [a free GitHub account](https://github.com/) or login if you already have one.  

On your GitHub profile click “new repo”, give it a name (like: django_rocks), brief description, choose the “public” repo option, and click “create repository”.  

In the command line, make sure you ```cd``` into your local django_rocks folder, and type:  

```git init```  

This initializes a git repository in your project. Next, type:  

```touch README```  

This creates a file called “README” in your directory.  

Then type:  

```git status```  

This will list out all the files in your working directory. Then:

```git add .```  

This adds all of your files & changes so far to a so-called staging area. With:  

```git commit -m "first commit"```  

... you commit all of your files, adding the message “first commit”  

Next type:  

```git remote add origin https://github.com/username/django_rocks.git```  

Your GitHub Repository page will list the repository URL, so feel free to copy and paste from there, rather than typing it in manually. You can copy and paste the link from your GitHub repository page by clicking the clipboard icon next to the URL. This creates a remote, or connection, named “origin” pointing at the GitHub repository you just created.  

With:  

```git push -u origin master```  

... you send your commits in your “master” branch to GitHub. Go check it out by going to the same url you used above: https://github.com/username/django_rocks (without the .git part)

If you want to continue making changes and pushing them to GitHub you’ll just need to use the following three commands:
<pre>
git add .  

git commit -m "type your commit message here"  

git push origin master  
</pre>

####Databases. Databases everywhere.
One last piece of boring info: we're using SQLite.  If you’re new to databases, or you’re just interested in trying Django, this is the easiest choice. SQLite is included in Python, so you won’t need to install anything else to support your database. You can edit your database settings in ```mysite/settings.py```. make sure you’ve created a database by this point. Do that with ```CREATE DATABASE database_name;``` within your database’s interactive prompt.  

While you’re editing mysite/settings.py, set ```TIME_ZONE``` to your time zone.  

Also, note the INSTALLED_APPS setting at the top of the file. That holds the names of all Django applications that are activated in this Django instance. Apps can be used in multiple projects, and you can package and distribute them for use by others in their projects. These applications are included by default as a convenience for the common case.  

Some of these applications makes use of at least one database table, though, so we need to create the tables in the database before we can use them. To do that, run the following command:  

```python manage.py migrate```  

The migrate command looks at the INSTALLED_APPS setting and creates any necessary database tables according to the database settings in your mysite/settings.py file and the database migrations shipped with the app. You’ll get a prompt asking you if you’d like to create a superuser account for the authentication system. Go ahead and do that.  


**Now you can dive into the [tutorial](https://docs.djangoproject.com/en/dev/intro/tutorial01/#creating-models). Happy coding!**
