FROM python:latest

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install pyqt5-dev-tools -y && \
	apt-get install openssh-server -y && \
	apt-get install git -y

RUN pip3 install --upgrade pip && \
	pip3 install tensorflow && \
	pip3 install pyqt5 && \
	pip3 install pyqt5-tools && \
	pip3 install pillow && \
	pip3 install lxml

RUN echo 'root:root' | chpasswd

RUN sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

WORKDIR /
RUN git clone https://github.com/hogbal/auto_labeling.git

WORKDIR auto_labeling
RUN pyrcc5 -o libs/resources.py resources.qrc

EXPOSE 22

RUN service ssh start
CMD ["/usr/sbin/sshd", "-D"]
