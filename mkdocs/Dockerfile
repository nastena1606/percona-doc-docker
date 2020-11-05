FROM alpine:latest

RUN apk --update --upgrade add --no-cache wget gcc musl-dev build-base jpeg-dev zlib-dev libffi-dev cairo-dev pango-dev gdk-pixbuf-dev python3 python3-dev py-pip fontconfig

RUN apk add --no-cache -X http://dl-cdn.alpinelinux.org/alpine/edge/testing py3-cairocffi

RUN apk add --no-cache font-noto
# percona.com site theme font
RUN wget --directory-prefix=/usr/share/fonts/TTF \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-Black.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-BlackItalic.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-Bold.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-BoldItalic.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-Italic.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-Light.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-LightItalic.ttf \
https://github.com/google/fonts/raw/master/ofl/chivo/Chivo-Regular.ttf

RUN fc-cache -f

WORKDIR /docs
COPY requirements.txt /docs
RUN pip install -r requirements.txt

EXPOSE 8000 443 80
CMD ["mkdocs","build"]
