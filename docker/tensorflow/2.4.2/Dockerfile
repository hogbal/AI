FROM tensorflow/tensorflow:2.4.2-gpu-jupyter

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install build-essential -y && \
	apt-get install pkg-config -y && \
	apt-get install libjpeg-dev libtiff5-dev libpng-dev -y && \
	apt-get install ffmpeg libavcodec-dev libavformat-dev libswscale-dev libxvidcore-dev libx264-dev libxine2-dev -y && \
	apt-get install libv4l-dev v4l-utils -y && \
	apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev -y && \
	apt-get install libgtk-3-dev -y && \
	apt-get install mesa-utils libgl1-mesa-dri libgtkgl2.0-dev libgtkglext1-dev -y && \
	apt-get install libatlas-base-dev gfortran libeigen3-dev -y && \
	apt-get install qt5-default -y && \
	apt-get install python3-dev python3-numpy -y && \
	apt-get install git -y && \
	apt-get install libgl1-mesa-glx -y && \
	apt-get install g++ openjdk-8-jdk -y && \
	apt-get install graphviz -y && \
	apt-get install wget -y && \
	apt install fonts-nanum-coding -y && \
	apt install protobuf-compiler -y && \
	apt install libssl-dev -y && \
	mkdir /tf/object-detection

RUN pip3 install --upgrade pip && \
	pip3 install jupyter_contrib_nbextensions && jupyter contrib nbextension install && \
	pip3 install autopep8 && \
	pip3 install cython && \
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
	pip3 install tf-models-official && \
	pip3 install tensorflow-text && \
	pip3 install pydot && \
	pip3 install pydotplus && \
	pip3 install tokenizer && \
	pip3 install sentencepiece && \
	pip3 install transformers && \
	pip3 install bert-for-tf2 && \
	pip3 install tokenizers && \
	pip3 install pandas-profiling && \
	pip3 install pylibjpeg pylibjpeg-libjpeg pydicom

RUN jupyter nbextension enable toc2/main && \
	jupyter nbextension enable code_prettify/autopep8 && \
	jupyter nbextension enable varInspector/main && \
	jupyter nbextension enable execute_time/ExecuteTime && \
	jupyter nbextension enable collapsible_headings/main

#setting cuda
RUN mv /usr/local/cuda/lib64/libcusolver.so.11 /usr/local/cuda/lib64/libcusolver.so.10
