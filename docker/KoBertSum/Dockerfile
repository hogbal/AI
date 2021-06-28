FROM pytorch/pytorch:1.9.0-cuda11.1-cudnn8-devel

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install vim -y && \
	apt-get install tmux -y && \
	apt-get install zsh -y && \
	apt-get install git -y && \
	apt-get install wget -y && \
	apt-get install language-pack-en -y && \
	update-locale

RUN pip install --upgrade pip && \
	pip install multiprocess && \
	pip install numpy && \
	pip install pyrouge && \
	pip install transformers && \
	pip install tensorboardX && \
	pip install torch && \
	pip install cpython && \
	pip install kss && \
	pip install bs4 && \
	pip install pandas && \
	pip install nltk && \
	pip install konlpy && \
	pip install tensorboard 

COPY KoBertSum /KoBertSum

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

WORKDIR /KoBertSum
CMD ["zsh"]
