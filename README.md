# Docker_NeuralNetwork_App
This repository joins all the code employed for constructing a Shiny App controlling R and Python versions in an empty Ubuntu 20.04 system. Furthermore, it is useful to connect R-python forcing tensorflow python environment.  


## Dockerfile
> FROM ubuntu:20.04

> WORKDIR /app

> COPY . /app

> CMD ["bin/bash"]


## Terminal 
> sudo docker build -t my_shiny_app_image .

> sudo docker run -p 1272:1272 my_shiny_app_image


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

> 

### Access to R to install all packages and their dependencies
> /usr/local/lib/R/bin/R

> 

>

>

>

>

