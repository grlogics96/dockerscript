FROM runpod/pytorch:3.10-1.13.1-116

ENV PYTHONUNBUFFERED=1

RUN pip install gdown

WORKDIR /workspace

RUN mkdir /workspace/auto-models

WORKDIR /workspace/auto-models

RUN gdown --fuzzy https://drive.google.com/file/d/1QxckuraM8G_bOvRsk_0h9MTtSpGRHgkz/view?usp=sharing
RUN gdown --fuzzy https://drive.google.com/file/d/1-D3JCHM8zYlQFwK4RAb8exs80YS_KZqO/view?usp=sharing

WORKDIR /workspace

ADD RNPD-A1111.ipynb .
ADD RNPD-Dreambooth-v1.ipynb .
ADD RNPD-Dreambooth-v2.ipynb .

ADD start.sh /start.sh
RUN chmod a+x /start.sh

SHELL ["/bin/bash", "--login", "-c"]
CMD [ "/start.sh" ]