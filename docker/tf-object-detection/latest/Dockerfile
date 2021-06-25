FROM tensorflow/tensorflow:latest-devel-gpu

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install python3-dev && \
	apt-get install wget -y && \
	apt-get install git -y && \
	apt-get install zsh -y && \
	apt-get install tmux -y && \
	apt-get install vim -y && \
	apt install protobuf-compiler -y

RUN pip3 install --upgrade pip && \
    pip3 install cython

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

#setting vim && tmux
COPY vimrc /root/.vimrc
COPY tmux.conf /root/.tmux.conf

#install oh my zsh
RUN chsh -s /usr/bin/zsh && \
	sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)" && \
	sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="agnoster"/' ~/.zshrc && \
	git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting && \
	git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions && \
	sed -i 's/plugins=(git)/plugins=(git zsh-syntax-highlighting zsh-autosuggestions)/' ~/.zshrc

CMD ["zsh"]
