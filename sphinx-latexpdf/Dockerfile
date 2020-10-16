FROM sphinxdoc/sphinx-latexpdf
WORKDIR /docs
ADD requirements.txt /docs
RUN apt-get update \
 && apt-get install -y wget \
 && apt-get autoremove \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*
RUN pip3 install -r requirements.txt
EXPOSE 5500
