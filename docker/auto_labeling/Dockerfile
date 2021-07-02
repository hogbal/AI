FROM ubuntu:20.04

RUN apt-get update && \
    apt-get upgrade -y && \
	apt-get install python3 -y && \
	apt-get install python3-pip -y && \
    apt-get install git -y && \
    apt install libxcb-xinerama0 -y

RUN pip3 install --upgrade pip && \
    pip3 install tensorflow && \
    pip3 install pyqt5 && \
    pip3 install pyqt5-tools && \
    pip3 install lxml && \
    pip3 install pillow
