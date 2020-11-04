FROM alpine:latest
WORKDIR /docs
RUN apk --update --upgrade add --no-cache gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig
RUN apk add --no-cache font-noto
RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi
ADD requirements.txt /docs
RUN pip install -r requirements.txt
EXPOSE 8000
CMD ["mkdocs","build"]
