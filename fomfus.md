#############################
########Ensure default python version is python3
#############################
(https://linuxconfig.org/how-to-change-default-python-version-on-debian-9-stretch-linux)

python --version
	-if python3 then you're done

sudo update-alternatives --list python
	-Will probably say no alternatives for python

list all available options:
ls /usr/bin/python*
	-looking for python2 and python3

Add options:
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.1 2
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.5 1
	-The integer at the end lists the priority. So python3.5 will be run first when in auto mode

Now try
python --version
	-it's probably still python2. So need to switch

sudo update-alternatives --config python
	-choose python3

check that it worked
python --version
	-should be python 3

#############################
####### Configure virtualenvwrapper
#############################
(https://virtualenvwrapper.readthedocs.io/en/latest/)

install virtualenvwrapper
pip install virtualenvwrapper

add to .bashrc:
export WORKON_HOME=~/Envs
source /usr/local/bin/virtualenvwrapper.sh

Now in folder you want to do work in:
mkvirtualenv env1

Can now install stuff, it's all stored in ~/Envs (good for dropbox, that's not backed up)

Useful commands:
lssitpackages - see what packages are installed in the virtualenv
workon XXX - switch to XXX env



# Django
