FROM python:3.12.1-slim-bullseye
USER root

RUN apt-get update && \
    apt-get -y install --reinstall ca-certificates && \
    apt-get -y install software-properties-common curl && \
    pip install --upgrade pip

# Install Basic Packages
RUN pip install ipykernel jupyter

# To have Jupyter export to PDF work uncomment next line. It is big!
# RUN apt-get install -y texlive-xetex texlive-fonts-recommended texlive-plain-generic jupyter-nbconvert
