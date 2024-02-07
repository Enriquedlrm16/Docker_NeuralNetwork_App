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
