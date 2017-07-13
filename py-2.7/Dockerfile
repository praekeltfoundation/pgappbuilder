FROM praekeltfoundation/pgappbuilder:latest

COPY requirements.txt /root/
COPY packages.txt /root/

RUN set -ex \
    && apt-get update \
    && apt-get install -y libpython-dev python curl \
    && curl https://bootstrap.pypa.io/get-pip.py | python \
    && apt-get install -y `cat /root/packages.txt` \
    && pip install --upgrade pip \
    && pip install -r /root/requirements.txt

