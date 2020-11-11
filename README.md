# percona-doc-docker

Docker files for [Percona](https://www.percona.com/software/documentation/) documentation builds.

- `mkdocs`: An Alpine-based image for building MkDocs/Markdown documentation.
- `sphinx`: Based on the official [Sphinx](https://hub.docker.com/u/sphinxdoc) `sphinxdoc/sphinx` image.

## Usage

### MkDocs projects

Perform a build (`mkdocs build`):

```sh
docker run --rm -v $(pwd):/docs perconalab/pmm-doc-md
```

Run the live preview local server (`mkdocs serve`):

```sh
docker run --rm -p 8000:8000 -v $(pwd):/docs perconalab/pmm-doc-md mkdocs serve -a 0.0.0.0:8000
```

Open your browser at <http://localhost:8000>

### Sphinx projects

For HTML:

```sh
docker run --rm -v $(pwd):/docs perconalab/percona-doc-sphinx make clean html
```

For PDF:

```sh
docker run --rm -v $(pwd):/docs perconalab/percona-doc-sphinx-latexpdf make latexpdf
```

Both assume a `./Makefile` and Sphinx source files in `./source`.

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
- [mkdocs-mermaid2-plugin](https://github.com/fralau/mkdocs-mermaid2-plugin) - For [mermaid](https://mermaid-js.github.io/mermaid/) diagrams.

### Sphinx image

Sphinx extensions:

- [sphinx-copybutton](https://sphinx-copybutton.readthedocs.io/) Adds a copy button to code blocks.
- [sphinx-tabs](https://pypi.org/project/sphinx-tabs/) Allows for tabbed content blocks.
- [sphinx_markdown_builder](https://pypi.org/project/sphinx-markdown-builder/) Writes Markdown files from rst sources.
- [sphinx_markdown_parser](https://pypi.org/project/sphinx-markdown-parser/) Allows for Markdown files in a Sphinx/rst project.
- [sphinxcontrib-srclinks](https://pypi.org/project/sphinxcontrib-srclinks/) Adds various page links (e.g. to Github) to navigation bar.
- [sphinx-reload](https://pypi.org/project/sphinx-reload/) Automatically rebuilds and serves a Sphinx project.
- [pymdown-extensions](https://facelessuser.github.io/pymdown-extensions/)
