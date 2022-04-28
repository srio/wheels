# wheels

Wheels created with dockers available in https://github.com/pypa/manylinux 

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


