FROM sphinxdoc/sphinx
WORKDIR /doc
ADD requirements.txt /doc
RUN apt-get update \
 && apt-get install -y wget \
 && apt-get autoremove \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*
RUN pip3 install -r requirements.txt
EXPOSE 5500
