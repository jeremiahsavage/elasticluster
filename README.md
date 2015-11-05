To run on CDIS cloud
--------------------
1. on gdc-login, set http{s}_proxy
```bash
$ export http_proxy=http://cloud-proxy:3128; export https_proxy=http://cloud-proxy:3128;
```
2. on gdc-login, locally install virtualenvwrapper
```bash
$ pip install virtualenvwrapper --user
$ echo "source ${HOME}/.local/bin/virtualenvwrapper.sh" >> ~/.bashrc
$ source ${HOME}/.local/bin/virtualenvwrapper.sh
```
3. on gdc-login, create a virtualenv for elasticluster using python2
```bash
$ mkvirtualenv --python /usr/bin/python2 p2
```
4. on gdc-login, clone elasticluster
```bash
$ git clone https://github.com/jeremiahsavage/elasticluster.git
```
5. on gdc-login, install elasticluster to p2 virtualenv
```bash
$ cd elasticluster
$ pip install -e .
```
6. on gdc-login, create elasticluster config file(ask for template config)
```bash
$ mkdir ~/.elasticluster
$ cp config ~/.elasticluster/
```
7. on gdc-login, start cluster
```bash
$ elasticluster start -vvv <cluster-name>
```
wait for all tasks to complete
8. on gdc-login, get ip of cluster frontend
```bash
$ nova list
```