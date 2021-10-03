FROM python:3

RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim

COPY requirements.txt .

RUN pip3 install --upgrade pip && \
    pip3 install --no-cache-dir -r requirements.txt \
    jupyterlab-horizon-theme
RUN rm -rf ~/.cache/pip

RUN pip3 install --upgrade --no-cache-dir \
    jupyterlab \
    jupyterlab-kite \
    jupyterlab_code_formatter

WORKDIR /src
COPY /src /src 
