FROM python:3

RUN apt-get update && apt-get install -y \
    sudo \
    wget \
    vim

RUN pip3 install --upgrade pip && \
    pip3 install --no-cache-dir -r requirements.txt \
    && rm -rf ~/.cache/pip

RUN pip3 install --upgrade --no-cache-dir \
    jupyterlab \
    jupyterlab-kite \
    jupyterlab_code_formatter \
    && rm -rf ~/.cache/pip \
    && jupyter labextension install \
    jupyterlab-horizon-theme \
    @ryantam626/jupyterlab_code_formatter \
    && jupyter serverextension enable --py jupyterlab_code_formatter

RUN cd && \
    wget https://linux.kite.com/dls/linux/current && \
    chmod 777 current && \
    sed -i 's/"--no-launch"//g' current > /dev/null && \
    ./current --install ./kite-installer

WORKDIR /home/work 
