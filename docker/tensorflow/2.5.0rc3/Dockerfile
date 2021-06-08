FROM tensorflow/tensorflow:2.5.0rc3-gpu-jupyter

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install libgl1-mesa-glx -y && \
	apt-get install g++ openjdk-8-jdk -y && \
	apt install fonts-nanum-coding -y && \
	pip3 install --upgrade pip && \
	pip3 install opencv-python && \
	pip3 install pandas && \
	pip3 install matplotlib && \
	pip3 install tqdm && \
	pip3 install tensorflow-addons && \
	pip3 install keras && \
	pip3 install scikit-learn && \
	pip3 install scipy && \
	pip3 install tensorboard_plugin_profile && \
	pip3 install elementpath && \
	pip3 install konlpy && \
	pip3 install wordcloud && \
	pip3 install tf-models-official==2.5.0rc3 && \
	pip3 install tensorflow-text==2.5.0rc3

