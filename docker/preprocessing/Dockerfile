FROM tensorflow/tensorflow:latest-gpu-jupyter

RUN apt-get install libgl1-mesa-glx -y
RUN pip3 install six numpy scipy Pillow matplotlib scikit-image opencv-python imageio Shapely && \
	pip3 install imgaug && \
	pip3 install tqdm && \
