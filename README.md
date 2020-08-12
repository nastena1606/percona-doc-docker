# pmm-doc-docker

Docker files for [Percona Monitoring and Management](percona.com/doc/percona-monitoring-and-management/2.x/) documentation builds.

- `mkdocs`: An Alpine-based image for building PMM's forthcoming MkDocs/Markdown documentation set for Percona Monitoring and Management (PMM)

- `sphinx`: Empty. (For future use.)

## Contents

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


