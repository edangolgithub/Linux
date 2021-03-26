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

```
Libraries have been installed in:
   /usr/local/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /bin/mkdir -p '/usr/local/bin'
  /bin/sh ./libtool   --mode=install /bin/install -c sqlite3 '/usr/local/bin'
libtool: install: /bin/install -c sqlite3 /usr/local/bin/sqlite3
 /bin/mkdir -p '/usr/local/include'
 /bin/install -c -m 644 sqlite3.h sqlite3ext.h '/usr/local/include'
 /bin/mkdir -p '/usr/local/share/man/man1'
 /bin/install -c -m 644 sqlite3.1 '/usr/local/share/man/man1'
 /bin/mkdir -p '/usr/local/lib/pkgconfig'
 /bin/install -c -m 644 sqlite3.pc '/usr/local/lib/pkgconfig'
make[1]: Leaving directory `/opt/sqlite-autoconf-3350200'
```

```
cd /opt/Python-x.y.z
LD_RUN_PATH=/usr/local/lib  ./configure
LD_RUN_PATH=/usr/local/lib make
LD_RUN_PATH=/usr/local/lib make altinstall
```
