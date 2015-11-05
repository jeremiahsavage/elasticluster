To run on CDIS cloud:
0. on gdc-login, set http{s}_proxy
```
$ export http_proxy=http://cloud-proxy:3128; export https_proxy=http://cloud-proxy:3128;
```

1. on gdc-login, locally install virtualenvwrapper
```
$ pip install virtualenvwrapper --user
$ echo "source ${HOME}/.local/bin/virtualenvwrapper.sh" >> ~/.bashrc
$ source ${HOME}/.local/bin/virtualenvwrapper.sh
```


2. on gdc-login, create a virtualenv for elasticluster using python2
```
$ mkvirtualenv --python /usr/bin/python2 p2
```

3. on gdc-login, clone elasticluster
```
$ git clone https://github.com/jeremiahsavage/elasticluster.git
```

4. on gdc-login, install elasticluster to p2 virtualenv
```
$ cd elasticluster
$ pip install -e .
```

5. on gdc-login, create elasticluster config file(ask for template config)
```
$ mkdir ~/.elasticluster
$ cp config ~/.elasticluster/
```

6. on gdc-login, start cluster
```
$ elasticluster start -vvv <cluster-name>
```
wait for all tasks to complete

7. on gdc-login, get ip of cluster frontend
```
$ nova list
```