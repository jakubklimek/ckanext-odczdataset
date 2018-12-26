# ckanext-odczdataset
CKAN extension for OpenData.cz extended Dataset and Resource attributes


# Extension installation into CKAN in Docker container

1. switch user to *root*
```bash
$ sudo su
```
2. go to CKAN's docker-compose directory
```bash
$ cd <CKAN-HOST-DIRECTORY>/contrib/docker
```
3. get into running *ckan* docker container
```bash
$ docker exec -it ckan /bin/bash -c "export TERM=xterm; exec bash"
```
4. activate the virtualenv 
```bash
ckan@<-ckandocker->$ source $CKAN_VENV/bin/activate && cd $CKAN_VENV/src/
```

5. clone and install this extension via *pip*
```bash
(venv)ckan@<-ckandocker->$ pip install -e "git+https://github.com/jakubklimek/ckanext-odczdataset#egg=ckanext-odczdataset"

```
6. enable extension by adding ```<SPACE>dataset_odczdataset``` into ``` ckan.plugins ``` line in  ```/etc/ckan/production.ini``` 

```bash
(venv)ckan@<-ckandocker->$ vim /etc/ckan/production.ini
```
```ini
...
ckan.plugins = <---YOUR PLUGINS---> dataset_odczdataset
...
```

7. exit *ckan* docker container
```bash
(venv)ckan@<-ckandocker->$ exit
```

8. restart *ckan* docker container
```bash
$ docker-compose restart ckan
```
9. check logs, if there is no error
```bash
$ docker-compose logs ckan
```
10. exit root su
```bash
$ exit
```
