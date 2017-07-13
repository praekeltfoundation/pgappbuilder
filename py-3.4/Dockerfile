FROM praekeltfoundation/pgappbuilder:latest

COPY requirements.txt /root/
COPY packages.txt /root/

RUN set -ex \
    && apt-get update \
    && apt-get remove -y python \
    && apt-get install -y libpython3-dev python3 curl \
    && update-alternatives --install /usr/bin/python python /usr/bin/python3 10 \
    && curl https://bootstrap.pypa.io/get-pip.py | python3 \
    && apt-get install -y `cat /root/packages.txt` \
    && pip install --upgrade pip \
    && pip install -r /root/requirements.txt

