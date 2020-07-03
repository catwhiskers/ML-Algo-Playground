FROM nvidia/cuda

RUN apt update -y; \
    add-apt-repository ppa:deadsnakes/ppa -y; \
    apt update -y; \
    apt install python3.8 -y 

#COPY NVIDIA_Nsight_Systems_Linux_2020.3.1.72.run /tmp/NVIDIA_Nsight_Systems_Linux_2020.3.1.72.run
#RUN chmod +x  /tmp/NVIDIA_Nsight_Systems_Linux_2020.3.1.72.run
#RUN /tmp/NVIDIA_Nsight_Systems_Linux_2020.3.1.72.run
RUN ln -s /usr/bin/python3 /usr/bin/python
RUN apt install python3-pip -y 
RUN ln -s /usr/bin/pip3 /usr/bin/pip
RUN apt install wget
RUN pip install torch
RUN pip install torchvision 
RUN wget https://raw.githubusercontent.com/pytorch/examples/master/mnist/main.py

ENTRYPOINT ["nvprof", "--print-gpu-trace", "python", "main.py"]



