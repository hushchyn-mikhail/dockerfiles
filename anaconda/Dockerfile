# docker-anaconda:201907_v1

# We wll use Ubuntu for our image
FROM ubuntu

# Updating Ubuntu packages
RUN apt-get update && yes|apt-get upgrade

# Adding wget and bzip2
RUN apt-get install -y wget bzip2

# Anaconda installing
RUN wget https://repo.continuum.io/archive/Anaconda3-2019.07-Linux-x86_64.sh
RUN bash Anaconda3-2019.07-Linux-x86_64.sh -b
RUN rm Anaconda3-2019.07-Linux-x86_64.sh

# Set path to conda
ENV PATH /root/anaconda3/bin:$PATH

# Updating Anaconda packages
RUN conda update conda
RUN conda update anaconda
RUN conda update --all

# Configuring Jupyter
RUN mkdir /opt/notebooks

# Install additional packages
RUN conda install pytorch torchvision cudatoolkit=10.0 -c pytorch


# Run instructions example
# sudo docker run -i -t --rm -p 8883:8883 --volume $(pwd)/<your_dir>:/opt/notebooks docker-anaconda /bin/bash -l -c "jupyter notebook --port 8883 --ip=* --allow-root --NotebookApp.token='' --NotebookApp.password=''"

