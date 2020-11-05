FROM alpine:latest

RUN apk --update --upgrade add --no-cache wget gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig

RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi

RUN apk add --no-cache font-noto ttf-inconsolata
RUN fc-cache -f

WORKDIR /docs
COPY requirements.txt /docs
RUN pip install -r requirements.txt

EXPOSE 8000
CMD ["mkdocs","build"]
