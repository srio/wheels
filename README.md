# wheels

Wheels created with dockers available in https://github.com/pypa/manylinux 

(after running ```python setup.py bdist_wheel``` we run ```auditwheel repair <WHEEL> --plat "manylinux2014_x86_64" -w wheels```  )

## Wheels (source/install)

- https://github.com/oasys-kit/oasys1-srwpy:  ```pip install --find-links https://github.com/srio/bob/wheels/ oasys_srwpy ```
- https://github.com/oasys-kit/shadow3/tree/devel-gfortran-yb66:  ```pip install --find-links https://silx.gitlab-pages.esrf.fr/bob/shadow3/ shadow3 ```

## Docker memorandum:

(it may need "sudo" before the command)

- Load docker: ```docker run -it quay.io/pypa/manylinux2010_x86_64 /bin/bash``` 
- To select python to use ```export PATH=/opt/python/cp36-cp36m/bin:${PATH}```
- List all running/stopped docker: ```docker ps -a```
- Stop a docker: ``` docker stop <CONTAINER ID>```
- Remove a docker: ``` docker rm <CONTAINER ID>```
- List images: ```docker images```
- Remove an image: ```docker rmi <IMAGE ID>```

## CentOS memorandum:

```
docker pull centos
docker run -it centos /bin/bash
...

cd /etc/yum.repos.d/
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
yum update -y
yum install wget
yum install git



```
