# SPDX-FileCopyrightText: 2023 SUSE LLC
#
# SPDX-License-Identifier: Apache-2.0

FROM registry.suse.com/bci/python:3.6

LABEL maintainer Pablo Suárez Hernández <psuarezhernandez@suse.com>

COPY requirements.txt /opt/
RUN zypper -n ref
RUN zypper -n install python3-PyYAML python3-salt python3-pip postgresql
RUN pip3.6 install -r /opt/requirements.txt

COPY uyuni_health_exporter.py /opt/
COPY config.yml /opt/

WORKDIR /opt/
ENTRYPOINT python3.6 /opt/uyuni_health_exporter.py
