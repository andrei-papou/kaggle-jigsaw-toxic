FROM jupyter/minimal-notebook:latest

# must reset to user root to install more stuff

# USER root
# apt-utils is missing and needed to avoid warning about skipping debconf
# RUN apt update && apt -y install apt-utils

# set the user back to original setting
# USER $NB_UID

RUN pip install --upgrade pip

# Move it up and put before requirements installation once the requirements cache is invalidated.
RUN pip install ipywidgets && jupyter nbextension enable --py --sys-prefix widgetsnbextension

COPY requirements.txt .
RUN pip install -r requirements.txt
