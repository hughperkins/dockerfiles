FROM ubuntu:14.04

RUN apt-get update && \
    apt-get install -y \
            git \
            gcc \
            g++ \
            wget \
            ocl-icd-libopencl1 \
            cmake-curses-gui \
            clinfo
RUN wget https://raw.githubusercontent.com/torch/ezinstall/master/install-deps && bash install-deps
RUN git clone https://github.com/torch/distro.git ~/torch --recursive
RUN cd ~/torch && chmod +x install.sh && bash ./install.sh
RUN . ~/torch/install/bin/torch-activate && luarocks install cltorch
RUN . ~/torch/install/bin/torch-activate && luarocks install clnn

CMD bash ~/torch/install/bin/th

