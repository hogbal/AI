FROM tensorflow/tensorflow:2.5.0rc1-gpu-jupyter

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get -y install libgl1-mesa-glx
RUN pip3 install --upgrade pip
RUN pip3 install opencv-python
RUN pip3 install pandas
RUN pip3 install matplotlib
RUN pip3 install tqdm
RUN pip3 install tensorflow-addons
RUN pip3 install keras
RUN pip3 install scikit-learn
RUN pip3 install scipy
RUN pip3 install tensorboard_plugin_profile
