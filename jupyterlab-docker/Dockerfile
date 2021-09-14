FROM python:3

RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim

COPY requirements.txt .

RUN pip3 install --upgrade pip && \
    pip3 install --no-cache-dir -r requirements.txt \
    && rm -rf ~/.cache/pip

RUN pip3 install --upgrade --no-cache-dir \
    jupyterlab \
    jupyterlab-kite \
    jupyterlab-horizon-theme \
    jupyterlab_code_formatter \
    && rm -rf ~/.cache/pip

WORKDIR /home/work
