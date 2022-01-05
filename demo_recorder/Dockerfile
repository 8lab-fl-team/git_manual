FROM ubuntu:20.04

WORKDIR /root/recorder
# 换源，删除secure相关的源
# 安装git、asciinema、vim几个必要组件
RUN bash -c "sed -i 's/http:\/\/archive.ubuntu.com\/ubuntu\//http:\/\/mirrors.tuna.tsinghua.edu.cn\/ubuntu\//g' /etc/apt/sources.list && \
            sed -i '/http:\/\/secur/d' /etc/apt/sources.list &&\ 
            apt update && \ 
            apt install python3-pip git wget zsh vim -y && \
            wget https://gitee.com/Devkings/oh_my_zsh_install/raw/master/install.sh &&\
            sh install.sh && rm install.sh -f &&\
            pip3 install asciinema"
ENV SHELL=/bin/bash
ENV TERM=xterm-256color
VOLUME [ "/root/recorder" ]
ENTRYPOINT [ "/bin/zsh" ]
