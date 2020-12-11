FROM alpine:latest

RUN apk --update --upgrade add --no-cache wget gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig graphviz git openjdk11-jre

RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi

# Fonts
RUN apk add --no-cache font-noto ttf-inconsolata
RUN mkdir -p /usr/share/fonts/chivo && cd /usr/share/fonts/chivo && wget -O Chivo.zip https://fonts.google.com/download?family=Chivo && unzip Chivo.zip
RUN fc-cache -f

WORKDIR /docs
COPY requirements.txt /docs
RUN pip install -r requirements.txt

# plantuml: Install local copy (remote access via setting in mkdocs.yml)
RUN mkdir -p /opt/plantuml && cd /opt/plantuml && wget -O plantuml.jar https://downloads.sourceforge.net/project/plantuml/plantuml.jar
COPY plantuml /usr/local/bin
RUN chmod +x /usr/local/bin/plantuml

EXPOSE 8000
CMD ["mkdocs","build"]
