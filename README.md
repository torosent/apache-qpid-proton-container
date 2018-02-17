# python-qpid-proton

Sample Dockerfile with Python 3.6 and Apache Qpid Proton

You can set the `PYTHON_IMAGE_VERSION` `PROTON_VERSION` `PYTHON_VERSION` when building the image.

For example:

```
docker build -t python-qpid-proton --build-arg PYTHON_IMAGE_VERSION=3.6-slim-stretch --build-arg PROTON_VERSION=0.18.1 --build-arg PYTHON__DIR_VERSION=3.6 .
```

To install Azure Event Hub SDK in Python, you can add to the Dockerfile:

```
RUN pip3 install lxml beautifulsoup4 azure-storage azure-servicebus
RUN git clone https://github.com/Azure/azure-event-hubs-python.git
WORKDIR /azure-event-hubs-python
RUN python3 setup.py install && pip3 install -e .
```
