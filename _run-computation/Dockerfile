FROM debian:stable-slim

LABEL "com.github.actions.name"="Trigger Comutation"
LABEL "com.github.actions.description"="Run the current computation."
LABEL "com.github.actions.icon"="refresh-cw"
LABEL "com.github.actions.color"="orange"

LABEL "repository"="https://github.com/faical-yannick-congo/corr-repo"
LABEL "homepage"="https://aical-yannick-congo.github.io/corr-repo"

RUN apt-get update && apt-get install \
    -y --no-install-recommends curl git python3 python3-virtualenv

COPY hub-linux-amd64-2.12.4.tgz /hub-linux-amd64-2.12.4.tgz
RUN tar -zxf /hub-linux-amd64-2.12.4.tgz -C / && rm /hub-linux-amd64-2.12.4.tgz
RUN /hub-linux-amd64-2.12.4/install

RUN python3 -m virtualenv --python=/usr/bin/python3 /opt/venv
RUN . /opt/venv/bin/activate && pip install --upgrade pip setuptools wheel

ADD entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]
