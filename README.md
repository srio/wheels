# wheels for the Oasys project

The easy installation of OASYS (https://oasys-kit.github.io/) requires creating wheels of three packages that contain C, C++ and/or fortran code: 

- https://github.com/oasys-kit/OASYS1-srwpy
- https://github.com/oasys-kit/shadow3
- https://github.com/tschoonj/xraylib

Wheels are required for 3 platforms (linux, MacOS and Windows). 

In Linux, the wheels are created with dockers available in https://github.com/pypa/manylinux, typically running ```python setup.py bdist_wheel``` and then we run ```auditwheel repair <WHEEL> --plat "manylinux2014_x86_64" -w wheels```.

The creationof wheels for different python version is automated using the ESRF bob system: https://gitlab.esrf.fr/silx/bob



## Status(available wheels)

in  bob: 

- oasys-srwpy: Linux [3.7-3.10], MacOS (intel): [TODO], MacOS (arm): [TODO], Windows [TODO] https://silx.gitlab-pages.esrf.fr/bob/oasys1-srwpy
- shadow3: Linux [3.7-3.10], MacOS (intel): [3.7-3.10], MacOS (arm): [TODO], Windows [TODO] https://silx.gitlab-pages.esrf.fr/bob/shadow3
- xraylib: Linux [3.7-3.10], MacOS (intel): [3.7-3.10], MacOS (arm): [TODO], Windows [NOT AVAILABLE] https://silx.gitlab-pages.esrf.fr/bob/xraylib

in pypi: 

- oasys-srwpy: Linux [3.7], MacOS: [3.7], Windows [3.7] https://pypi.org/project/oasys-srwpy/
- shadow3 v 18.5.30: Linux [3.7], MacOS (intel): [3.7], Windows [3.7] https://pypi.org/project/shadow3
- xraylib: Linux [3.7-3.10], MacOS (intel): [3.7], Windows [NOT AVAILABLE] https://pypi.org/project/xraylib

in shadow3 github:

- shadow3 v 22.2.7: Linux [3.7-3.9], MacOS (intel): [3.7], Windows [3.7] https://github.com/oasys-kit/shadow3/tree/devel-gfortran-yb66/wheels



## Other information

### bob repositories (source/install)

- SRW: https://silx.gitlab-pages.esrf.fr/bob/oasys1-srwpy/ ```pip install oasys1-srwpy --pre --find-links https://silx.gitlab-pages.esrf.fr/bob/oasys1-srwpy/```
- SHADOW3: https://silx.gitlab-pages.esrf.fr/bob/shadow3/ ```pip install shadow3 --pre --find-links https://silx.gitlab-pages.esrf.fr/bob/shadow3/```
- XRAYLIB: https://silx.gitlab-pages.esrf.fr/bob/xraylib/ ```pip install xraylib --pre --find-links https://silx.gitlab-pages.esrf.fr/bob/xraylib/```

### Docker memorandum:

(it may need "sudo" before the command)

- Load docker: ```docker run -it quay.io/pypa/manylinux2010_x86_64 /bin/bash``` 
- To select python to use ```export PATH=/opt/python/cp36-cp36m/bin:${PATH}```
- List all running/stopped docker: ```docker ps -a```
- Stop a docker: ``` docker stop <CONTAINER ID>```
- Remove a docker: ``` docker rm <CONTAINER ID>```
- List images: ```docker images```
- Remove an image: ```docker rmi <IMAGE ID>```

### CentOS memorandum:

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
