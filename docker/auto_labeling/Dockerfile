FROM ubuntu:20.04

ENV PATH /usr/local/bin:$PATH
ENV LANG C.UTF-8

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install git -y && \
	apt-get install python3 python3-dev python3-pip python3-setuptools python3-wheel gcc -y && \
	apt-get install pyqt5-dev-tools -y

RUN pip3 install --upgrade pip && \
	pip3 install tensorflow && \
	pip3 install pyqt5 && \
	pip3 install pyqt5-tools

RUN pyrcc5 -o libs/resources.py resources.qrc
