ARG BASE_IMAGE=mcr.microsoft.com/devcontainers/python:1-3.12-bullseye
FROM ${BASE_IMAGE} AS base

RUN apt-get update \
 && apt-get install -y \
        curl \
        gcc \
        git \
        libldap2-dev \
        libsasl2-dev \
        libssl-dev \
        sqlite3 \
 && rm -rf /var/lib/apt/lists/*

# install reqs
WORKDIR /tmp
COPY requirements.txt optional-requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install --no-cache-dir -r optional-requirements.txt
