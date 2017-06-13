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
