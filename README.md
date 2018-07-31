# Setting up `virtualenv`

- `WORKON_HOME` defines where the virtual environment should live.
- `PROJECT_HOME` defines the location of the development projects.

```shell
export WORKON_HOME=${HOME}/.virtualenvs
export PROJECT_HOME=${HOME}/django-projects
source /usr/share/virtualenvwrapper/virtualenvwrapper.sh
```

# Creating a virtual environment

- Create a new virtual environment.

```shell
$ mkvirtualenv -p /usr/bin/python3.5 readit
Running virtualenv with interpreter /usr/bin/python3.5
Using base prefix '/usr'
New python executable in /home/user1/.virtualenvs/readit/bin/python3.5
Also creating executable in /home/user1/.virtualenvs/readit/bin/python
```

- To stop working on the virtual environment, use the `deactivate` command.
- To start working on the virtual environment, use the `workon <project>` command.

```shell
(readit) user1@server:~/django-projects$ deactivate 
user1@server:~/django-projects$ workon readit
(readit) user1@server:~/django-projects$ 
```
# Install `MySQL`

- Follow this link.

[https://www.digitalocean.com/community/tutorials/how-to-create-a-django-app-and-connect-it-to-a-database][https://www.digitalocean.com/community/tutorials/how-to-create-a-django-app-and-connect-it-to-a-database]

# Install `django`

- Install `django` with `pip` and confirm the installation with `pip freeze`.

```shell
$ pip install django
Collecting django
  Downloading https://files.pythonhosted.org/packages/ab/15/cfde97943f0db45e4f999c60b696fbb4df59e82bbccc686770f4e44c9094/Django-2.0.7-py3-none-any.whl (7.1MB)
    100% |████████████████████████████████| 7.1MB 28.4MB/s 
Collecting pytz (from django)
  Downloading https://files.pythonhosted.org/packages/30/4e/27c34b62430286c6d59177a0842ed90dc789ce5d1ed740887653b898779a/pytz-2018.5-py2.py3-none-any.whl (510kB)
    100% |████████████████████████████████| 512kB 299kB/s 
Installing collected packages: pytz, django
Successfully installed django-2.0.7 pytz-2018.5

$ pip freeze
Django==2.0.7
pkg-resources==0.0.0
pytz==2018.5
```

# Create a local `pip` repository

- Install `python3-pip` and `pip2pi`. Become `root` first for `pip2pi`.
```shell
apt install python3-pip
sudo su -
pip3 install pip2pi
```
- Create a local `pip` directory `/opt/pip`. Download `pip` packages to this directory and run `dir2pi`. Finally, copy `/opt/pip` to `/var/www/html/` for web hosting.

```shell
mkdir /opt/pip
pip3 install --download /opt/pip django==2.0.6
dir2pi /opt/pip
cp -av /opt/pip /var/www/html/
```
# Using `MySQL` with `django`

- Install `mysql`.

```shell
apt install mysql-server
apt install libmysqlclient-dev
```

- Install `django` and `SQL` client.

```shell
cat requirements.txt 
django==2.0.6
mysqlclient==1.3.12
pip3 install -r requirements.txt
```

# Starting the project

- Move into the project directory and create a project.

```shell
$ cd django-projects/
$ django-admin startproject readit
```
