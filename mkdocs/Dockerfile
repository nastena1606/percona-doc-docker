FROM alpine:latest
RUN apk add --no-cache gcc musl-dev build-base python3 python3-dev py-pip && pip install mkdocs mkdocs-macros-plugin mkdocs-exclude mkdocs-redirects mkdocs-img2fig-plugin mkdocs-table-reader-plugin markdown-strikethrough mkdocs-material
WORKDIR /docs
EXPOSE 8000
CMD ["mkdocs","build"]
