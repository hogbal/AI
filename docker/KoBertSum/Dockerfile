FROM tensorflow/tensorflow:latest-devel-gpu

RUN mv /usr/local/cuda/lib64/libcusolver.so.11 /usr/local/cuda/lib64/libcusolver.so.10

RUN git clone https://github.com/uoneway/KoBertSum.git

WORKDIR KoBertSum

RUN python3 main.py -task install
RUN sed -it 's/python make_data.py -task train_bert -target_summary_sent abs -n_cpus/python make_data.py -task train_bert -target_summary_sent ext -n_cpus/' main.py
RUN sed -it 's/extractive_test_v2.jsonl/test.jsonl/' src/make_data.py
