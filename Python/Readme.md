```
sudo yum groupinstall "Development Tools"
sudo wget https://www.python.org/ftp/python/3.9.2/Python-3.9.2.tgz
sudo tar xzf Python-3.9.2.tgz 
cd Python-3.9.2 
sudo ./configure --enable-optimizations 
sudo make altinstall 
```
```
PATH=$PATH:/usr/local/bin
alias python3=python3.9
alias venv="source $HOME/env/bin/activate"
```
```
venv
```

```
python3 -m venv env
source env/bin/activate
```



```
python -m pip install Django
django-admin startproject mysite
python manage.py startapp polls
python manage.py runserver

```
```
cd ~ && wget https://www.sqlite.org/2020/sqlite-autoconf-3320100.tar.gz && tar xvfz sqlite-autoconf-3320100.tar.gz && cd sqlite-autoconf-3320100 && ./configure && make && make install
```
