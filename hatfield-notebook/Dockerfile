# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
FROM jupyter/all-spark-notebook

MAINTAINER Adam Soltys <asoltys@hatfieldgroup.net>

USER $NB_USER

# R packages
RUN conda install --quiet --yes \
    'r-jsonlite=1.1' \
    'r-httr=1.2.1' \
    && conda clean -tipsy 

USER $NB_USER
RUN conda install --quiet --yes conda-build \
    && mkdir /home/jovyan/channel \
    && cd /home/jovyan/channel \
    && conda skeleton cran --cran-url=http://stats.hatfieldgroup.net/cran/ wrdr \
    && cd /home/jovyan \
    && export CONDA_BLD_PATH=/home/jovyan/channel \
    && conda build channel \
    && conda index channel \
    && conda install --quiet --yes r-wrdr -c file:///home/jovyan/channel

