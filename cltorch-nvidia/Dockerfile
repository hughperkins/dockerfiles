FROM hughperkins/cltorch:latest

RUN apt-get update -y && \
    apt-get install -y cmake-curses-gui \
                       clinfo
# RUN wget http://us.download.nvidia.com/XFree86/Linux-x86_64/352.55/NVIDIA-Linux-x86_64-352.55.run
RUN wget http://us.download.nvidia.com/XFree86/Linux-x86_64/346.96/NVIDIA-Linux-x86_64-346.96.run
RUN chmod +x NVIDIA-Linux-x86_64-3*.run 
RUN ./NVIDIA-Linux-x86_64-3*.run -s --no-kernel-module
RUN cd ~ && mkdir git && cd git && git clone --recursive https://github.com/hughperkins/EasyCL.git
RUN cd ~/git/EasyCL && mkdir build && cd build && cmake -DBUILD_TESTS=ON -DCMAKE_BUILD_TYPE=Debug .. && make -j 4 install

CMD ~/torch/install/bin/th -l cltorch

