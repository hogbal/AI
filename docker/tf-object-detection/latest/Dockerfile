FROM tensorflow/tensorflow:latest-devel-gpu

#setting cuda
RUN mv /usr/local/cuda/lib64/libcusolver.so.11 /usr/local/cuda/lib64/libcusolver.so.10

#install tensorflow 2 object detection api
WORKDIR /tf/object-detection

RUN git clone --depth 1 https://github.com/tensorflow/models && \
	git clone https://github.com/cocodataset/cocoapi.git

WORKDIR /tf/object-detection/cocoapi/PythonAPI

RUN make && \
	cp -r pycocotools /tf/object-detection/models/research

WORKDIR /tf/object-detection/models/research

RUN protoc object_detection/protos/*.proto --python_out=. && \
	cp object_detection/packages/tf2/setup.py . && \
	python3 -m pip install .

WORKDIR /tf
