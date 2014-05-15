# ubuntu Dockerfile

FROM ubuntu:12.04

# update OS
RUN echo "deb http://mirrors.163.com/ubuntu/ precise main universe multiverse" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

# Install basic packages
RUN apt-get install -y software-properties-common
RUN apt-get install -y curl git htop unzip vim wget

# Add files
ADD root/.bashrc /root/.bashrc
ADD root/.gitconfig /root/.gitconfig
ADD root/scripts /root/scripts

ENV HOME /root
WORKDIR /root

