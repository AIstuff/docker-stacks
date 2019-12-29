# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=jupyter/scipy-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_13.x | bash -
RUN apt-get install -y nodejs

# Install typescript and javascript kernels
RUN npm install -g itypescript ijavascript
RUN its --ts-install=global
RUN ijsinstall

# Install Tensorflow
RUN pip install --quiet \
    'tensorflow==2.0.0' torch torchvision && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER
