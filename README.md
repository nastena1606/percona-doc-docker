# percona-doc-docker

Docker files for [Percona](https://www.percona.com/software/documentation/) documentation builds.

- `mkdocs`: An Alpine-based image for building MkDocs/Markdown documentation.
- `sphinx`: Based on the official [Sphinx](https://hub.docker.com/u/sphinxdoc) `sphinxdoc/sphinx` image.

## Contents

### MkDocs image

Alpine packages:

- python3
- python3-dev
- py-pip

For MkDocs, MkDocs plugins and dependencies (mainly [WeasyPrint](https://weasyprint.org/)):

- build-base
- cairo-dev
- gcc
- gdk-pixbuf-dev
- jpeg-dev
- libffi-dev
- musl-dev
- pango-dev
- zlib-dev

MkDocs packages and plugins:

- [mkdocs](https://www.mkdocs.org/)
- [mkdocs-macros-plugin](https://pypi.org/project/mkdocs-macros-plugin/)
- [mkdocs-exclude](https://pypi.org/project/mkdocs-exclude/)
- [mkdocs-table-reader-plugin](https://pypi.org/project/mkdocs-table-reader-plugin/)
- [mkdocs-material](https://pypi.org/project/mkdocs-material/)
- [mkdocs-with-pdf](https://pypi.org/project/mkdocs-with-pdf/) - Depends on [WeasyPrint](https://weasyprint.readthedocs.io/) which depends on `py3-cairocffi` which doesn't have a wheel and for which the Alpine package is currently in the testing repo and is hence installed separately.

### Sphinx image

Sphinx extensions:

- [sphinx-copybutton](https://sphinx-copybutton.readthedocs.io/) Adds a copy button to code blocks.
- [sphinx-tabs](https://pypi.org/project/sphinx-tabs/) Allows for tabbed content blocks.
- [sphinx_markdown_builder](https://pypi.org/project/sphinx-markdown-builder/) Writes Markdown files from rst sources.
- [sphinx_markdown_parser](https://pypi.org/project/sphinx-markdown-parser/) Allows for Markdown files in a Sphinx/rst project.
- [sphinxcontrib-srclinks](https://pypi.org/project/sphinxcontrib-srclinks/) Adds various page links (e.g. to Github) to navigation bar.
- [sphinx-reload](https://pypi.org/project/sphinx-reload/) Automatically rebuilds and serves a Sphinx project.
- [pymdown-extensions](https://facelessuser.github.io/pymdown-extensions/)
