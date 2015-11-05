To run on CDIS cloud
--------------------
1. on login-node, set http{s}_proxy

        $ export http_proxy=http://cloud-proxy:3128; export https_proxy=http://cloud-proxy:3128;

2. on login-node, locally install virtualenvwrapper

        $ pip install virtualenvwrapper --user
        $ echo "source ${HOME}/.local/bin/virtualenvwrapper.sh" >> ~/.bashrc
        $ source ${HOME}/.local/bin/virtualenvwrapper.sh

3. on login-node, create a virtualenv for elasticluster using python2

        $ mkvirtualenv --python /usr/bin/python2 p2

4. on login-node, clone elasticluster

        $ git clone https://github.com/jeremiahsavage/elasticluster.git

5. on login-node, install elasticluster to p2 virtualenv

        $ cd elasticluster
        $ pip install -e .

6. on login-node, create elasticluster config file(ask for template config)

        $ mkdir ~/.elasticluster
        $ cp config ~/.elasticluster/

7. on login-node, start cluster. wait for all tasks to complete

        $ elasticluster start -vvv <cluster-name>

8. on login-node, get ip of cluster frontend

        $ nova list

9. on login-node, ssh into cluster frontend

        $ elasticluster ssh <cluster-name>
