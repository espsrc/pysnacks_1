FROM jupyter/datascience-notebook:ubuntu-20.04


USER root

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
RUN apt-get install -y htop btop++

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

USER $NB_USER

RUN cd /opt/install && \
    conda env update -n base --file environment.yml && \
    mv /opt/conda/.condarc /opt/conda/.condarc.bak && \
    wget --output-document sostat2021.env.yml https://raw.githubusercontent.com/spsrc/sostat2021/main/environment.yml && \
    conda env update -n base --file sostat2021.env.yml && \
    conda install --yes -c conda-forge nbgitpuller git && \
    conda clean --all --yes
