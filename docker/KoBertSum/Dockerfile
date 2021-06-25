FROM tensorflow/tensorflow:latest-devel-gpu

RUN mv /usr/local/cuda/lib64/libcusolver.so.11 /usr/local/cuda/lib64/libcusolver.so.10
RUN git clone https://github.com/uoneway/KoBertSum.git

WORKDIR KoBertSum

RUN python3 main.py -task install
RUN sed -it 's/python make_data.py -task train_bert -target_summary_sent abs -n_cpus/python make_data.py -task train_bert -target_summary_sent ext -n_cpus/' main.py
RUN sed -it 's/extractive_test_v2.jsonl/test.jsonl/' src/make_data.py

RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install vim -y && \
	apt-get install tmux -y && \
	apt-get install zsh -y

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
