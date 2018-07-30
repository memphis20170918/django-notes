# Setting `virtualenv`

- `WORKON_HOME` defines where the virtual environment should live.
- `PROJECT_HOME` defines the location of the development projects.
- 

```shell
export WORKON_HOME=${HOME}/.virtualenvs
export PROJECT_HOME=${HOME}/django-projects
source /usr/share/virtualenvwrapper/virtualenvwrapper.sh
```

# Local `pip` repository

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
# django with mysql

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
