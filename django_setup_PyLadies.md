###Django unchained - a PyLadies story

In the early days, Web developers wrote every page by hand. Updating a Web site meant editing HTML; a “redesign” involved redoing every single page, one at a time.  
As Web sites grew and became more ambitious, it quickly became obvious that that situation was tedious, time-consuming, and ultimately untenable. PHP fixed many of these problems, and it took the world by storm – it’s now by far the most popular tool used to create dynamic Web sites, and dozens of similar languages and environments (ASP, JSP, etc.) followed PHP’s design closely. PHP’s major innovation is its ease of use: PHP code is simply embedded into plain HTML; the learning curve for someone who already knows HTML is extremely shallow. 
third-generation” Web development frameworks. These frameworks – Django and Ruby on Rails appear to be the most popular these days – recognize that the Web’s importance has escalated of late. With this new explosion of Web development comes yet another increase in ambition; Web developers are expected to do more and more every day.  
Django was invented to meet these new ambitions. Django lets you build deep, dynamic, interesting sites in an extremely short time. Django is designed to let you focus on the fun, interesting parts of your job while easing the pain of the repetitive bits.  

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
