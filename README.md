## Prerequisites
### install Virtualbox
https://www.virtualbox.org/wiki/Downloads

### install & run Docker and boot2docker on OSX
```
$ brew install docker boot2docker 
$ boot2docker init
$ boot2docker start
# set env as boot2docker directed as a result of the command above.
$ boot2docker up

```




## How To Use

### CentOS7 for AWS
```
$ git clone git@github.com:forthelocal/Dockerfiles.git
$ cd Dockerfiles/centos7
$ vi Dockerfile # you need to modify authorized_keys part.
$ docker build .
```

