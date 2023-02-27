ARG BASE_CONTAINER=jupyter/scipy-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Benjamin John Winjum <bwinjum@oarc.ucla.edu"

RUN conda install -c conda-forge py-xgboost && \
    pip install dtreeviz[xgboost]

USER root
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
  && apt-get -y install --no-install-recommends \
  graphviz \
  patch \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
USER $NB_UID

RUN pip install nltk

