FROM alpine:latest

RUN apk --update --upgrade add --no-cache wget gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig graphviz

RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi

RUN apk add --no-cache font-noto ttf-inconsolata
RUN fc-cache -f

WORKDIR /docs
COPY requirements.txt /docs
RUN pip install -r requirements.txt

# plantuml can be accessed remotely via setting in mkdocs.yml
# RUN mkdir -p /opt/plantuml && cd $_ && wget -O plantuml.jar http://sourceforge.net/projects/plantuml/files/plantuml.jar/download

EXPOSE 8000
CMD ["mkdocs","build"]
