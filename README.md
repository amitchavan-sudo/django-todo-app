# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)

A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :

# our app "aws ec2 ubuntu , git,github,docker,jenkins "
 
After the successfully deploing our app on vs code


Now the time to automate the app deployment using "aws ec2 ubuntu , git,github,docker,jenkins "


first  run our project manually on aws ec2 ubuntu 

step1:
make directory in aws ec2 ubuntu 
```bash
mkdir projects
cd projects
```

step2 :
clone the code form github

```bash 
$ git clone https://github.com/amitchavan-sudo/django-todo.git

ls 
cd project name 
```

step3:now install requirements

```bash
$ sudo apt update
$ sudo apt install python3-pip
$ sudo pip3 install django
$ sudo apt update 
```
setp4:now creat a environment and activate environment
```bash
$ sudo python3 -m venv myenv
$ sudo source myenv/bin/activate
```

step5: now apply migrations 
```bash 
$ sudo python3 manage.py migrate 
```
step6:now make rh app live 
```bash
$ sudo python3 manage.py runserver
```

#Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

# now we run project wit dockerfile 

step1: install docker 

```bash
$ sudo apt update 
$ sudo apt install docker .io
```

step2:write a docker file 

```bash
$ vi dockerfile 
# tab i for insert 
FROM python:3.9-slim
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
RUN sudo python3 manage.py migrate 
EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# press Esc and :wq and out form the vi file 
```

step4:build a docker image 
```bash
$ sudo docker build . -t todo-app #('todo-app'is the name of image )
```

step5 :run a docker container 
```bash 
$ sudo docker run -p 8000:8000 todo-app #for run your containr 
# ctrl +c to back your terminal

$ sudo docker -d -p 8000:8000 todo-app #command for your container run in background 
```

#Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

# now run our project with jenknis  and docker 

step1:

```bash
$ sudo apt update 
$ sudo apt install docker .io
```

step2:write a docker file 

```bash
$ vi dockerfile 
# tab i for insert 
FROM python:3.9-slim
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
RUN sudo python3 manage.py migrate 
EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# press Esc and :wq and out form the vi file 
```

step4:install jenkins

```bash
install jenkinse manually  useing this link (https://www.trainwithshubham.com/blog/install-jenkins-on-aws)

install jenkins using docker 
$ sudo docker pull jenkins/jenkins #this command install jenkins latest image

```
step4: now run our jenkins image 

```bash
$ sudo docker run -p 8080:8080 (our jenkins imaege id /name) #run jenkins image 
ctrl+c is back to our container 

$ sudo docker run -d -p 8080:8080 (our jenkins imaege id /name) # run for background 

$ sudo sudo systemctl enable jenkins
$ sudo systemctl start jenkins
$ sudo systemctl status jenkins
```

#Once the  jenkins  is hosted, head over to 127.0.0.1:8080  for the App. ( 127.0.0.1 replace this ip with our machine pubalic ip )

first download jenkins plugins 
set up your username ,pass ,gmail 
now go on jenknis and setup your ci-cd 


              *welcome to jenkins *

click on set up agent 

new node screen 
add node name (todo-app-dev) 
select permanant agent and ok

after this new window is open 
name :todo-app-dev
description:the node is for todo app cicd
number of excuters :1
root dir:past your root dir
lable :todo dev
use web socket
no fill other info

creat note for todo-app 

**********************************************

after creating node go on dashboard 
click on creat a job 
enter item name :todo-dev
select free style project

 click ok

screen shift on genral name window 


now give all permisons to your projects dir #this  do in only ubuntu do not write on shell commannd its for permisons only 
```bash
$ sudo chmod 777 django-todo/
```
go on build step (here excute your build steps)
#here writw your project location on ubntu(pwd command gives you your locataion)
```bash
$ cd /home/ubuntu/projects/django-todo
$ docker build . -t todo-dev
$ docker run -d -p 8000:8000 todo-dev
```
click on save 

your pipeline is ready go and click on build now 

                                        THANK YOU 

