FROM alpine:latest
RUN apk --update --upgrade add --no-cache gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig
RUN apk add --no-cache font-noto
RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi
RUN pip install -U mkdocs mkdocs-macros-plugin mkdocs-exclude mkdocs-material mkdocs-with-pdf
WORKDIR /docs
EXPOSE 8000
CMD ["mkdocs","build"]
