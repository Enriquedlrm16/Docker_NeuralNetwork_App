# Docker_NeuralNetwork_App
This repository joins all the code employed for constructing a Shiny App controlling R and Python versions in an empty Ubuntu 20.04 system. Furthermore, it is useful to connect R-python forcing tensorflow python environment.  


## Dockerfile
> FROM ubuntu:20.04

> WORKDIR /app

> COPY . /app

> CMD ["bin/bash"]


## Terminal 
> sudo docker build -t my_nn_app_shiny .

> sudo docker run -it my_nn_app_shiny /bin/bash


### As a root... inside the docker
> apt-get update

> apt-get install -y g++ gfortran libreadline6-dev libx11-dev libxt-dev libpng-dev libjpeg-dev libcairo2-dev xvfb libbz2-dev libzstd-dev liblzma-dev libcurl4-openssl-dev texinfo texlive texlive-fonts-extra screen wget libpcre2-dev zlib1g-dev libbz2-dev liblzma-dev libpcre2-dev libcurl4-openssl-dev openjdk-11-jdk make libssl-dev zlib1g-dev libncurses5-dev libncursesw5-dev libreadline-dev libsqlite3-dev libgdbm-dev libdb5.3-dev libbz2-dev libexpat1-dev liblzma-dev libffi-dev libc6-dev libharfbuzz-dev libfreetype6-dev libfribidi-dev libfftw3-dev nano build-essential git libxml2-dev libglpk-dev libhdf5-dev libgsl-dev

> cd /usr/local/src

> wget https://cran.rstudio.com/src/base/R-4/R-4.0.3.tar.gz

> cd R-4.0.3

> tar zxvf R-4.0.3.tar.gz

> ./configure --enable-R-shlib

> make

> make install

> /usr/local/lib/R/bin/R --version


## Ensure to download source packages (of the most relevant ones in your app) in their specific versions by locating and downloading them directly from CRAN 
> wget https://cran.r-project.org/src/contrib/Archive/SeuratObject/SeuratObject_4.0.2.tar.gz

> wget https://cran.r-project.org/src/contrib/Archive/Seurat/Seurat_4.0.3.tar.gz

> wget https://cran.r-project.org/src/contrib/Archive/Shiny_1.6.0.tar.gz

### Access to R to install all packages and their dependencies
> /usr/local/lib/R/bin/R

> install.packages('igraph', version = '1.2.6')

> install.packages('tensorflow', version = '2.13')

> install.packages('reticulate', version = '1.30.0')

> reticulate::install_python(version = '3.8')

> tensorflow::install_tensorflow(version = '2.13.0')

> reticulate::py_config()

python:         /root/.virtualenvs/r-tensorflow/bin/python
libpython:      /root/.pyenv/versions/3.8.18/lib/libpython3.8.so
pythonhome:     /root/.virtualenvs/r-tensorflow:/root/.virtualenvs/r-tensorflow
version:        3.8.18 (default, Feb  5 2024, 16:05:15)  [GCC 9.4.0]
numpy:          /root/.virtualenvs/r-tensorflow/lib/python3.8/site-packages/numpy
numpy_version:  1.24.3
tensorflow:     /root/.virtualenvs/r-tensorflow/lib/python3.8/site-packages/tensorflow

NOTE: Python version was forced by import("tensorflow")

>


