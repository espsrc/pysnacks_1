FROM jupyter/minimal-notebook:latest

USER root

MAINTAINER mparra@iaa.es

RUN apt-get -y update \
 && apt-get install -y dbus-x11 \
   firefox \
   xfce4 \
   xfce4-panel \
   xfce4-session \
   xfce4-settings \
   xorg \
   xubuntu-icon-theme

RUN apt-get install -y vim
RUN apt-get install -y htop

# Remove light-locker to prevent screen lock
RUN wget 'https://sourceforge.net/projects/turbovnc/files/2.2.5/turbovnc_2.2.5_amd64.deb/download' -O turbovnc_2.2.5_amd64.deb && \
   apt-get install -y -q ./turbovnc_2.2.5_amd64.deb && \
   apt-get remove -y -q light-locker && \
   rm ./turbovnc_2.2.5_amd64.deb && \
   ln -s /opt/TurboVNC/bin/* /usr/local/bin/

# apt-get may result in root-owned directories/files under $HOME
RUN chown -R $NB_UID:$NB_GID $HOME

ADD . /opt/install
RUN fix-permissions /opt/install

RUN echo "c.LabApp.collaborative = True" >> /etc/jupyter/jupyter_notebook_config.py
RUN echo "c.LabApp.collaborative = True" >> /etc/jupyter/jupyter_server_config.py

USER $NB_USER

RUN cd /opt/install && \
    conda env update -n base --file environment.yml && \
    mv /opt/conda/.condarc /opt/conda/.condarc.bak && \
    wget --output-document pysnacks.env.yml https://raw.githubusercontent.com/spsrc/pysnacks_1/main/environment.yml && \
    conda env update -n base --file pysnacks.env.yml && \
    conda install --yes -c conda-forge nbgitpuller git && \
    conda clean --all --yes
