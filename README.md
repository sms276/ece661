# ece661

Course notes for ECEN 661 Applied EM and Optics at BYU, by Dr. Stephen Schultz.

Read it online: https://sms276.github.io/ece661/

## Installation

To install the software needed to build the book, run (from the command line):

```
pip install -r requirements.txt
```

This includes numpy, scipy, and matplotlib--packages you may need for examples
in the course notebooks.

## Build

From the command line, run (in the toplevel directory):

```
jb build book
```

This will output the static site in the directory `book/_build/html/`. To view
the site, open the file `book/_build/html/index.html` in a web browser, or run
the following command from the command line:

Linux, MacOS:

```bash
jb serve book
```

Windows:

```
cd book/_build/html
python -m http.server
```

Then open the URL http://localhost:8000 in a web browser.

The book is also hosted on GitHub Pages at https://sms276.github.io/ece661/.
It is automatically built on every commit to the master branch.

By default, the book only builds the pages that have changed since the last
build. To force a full rebuild, run

```
jb clean book
jb build book
```

## Writing

The book is written in Jupyter notebooks. Jupyter notebooks support Markdown
cells and code cells, among others. To learn the basic markdown syntax, see

* https://myst-parser.readthedocs.io/en/latest/

To learn about UI elements, page layouts, and more about writing content for
JupyterBook, see

* https://jupyterbook.org/en/stable/intro.html

For theme configuration options, see

* https://sphinx-book-theme.readthedocs.io/en/stable/index.html

Some example files and notebooks can be found under ``/examples``.

To add content, create a new notebook file under ``/book/pages``. Be sure to
then include it in the ``_toc.yml`` file under ``/book``. The order of the
files in ``_toc.yml`` determines the order of the pages in the book. The first
level heading in the notebook will be used as the page title and appear in the
table of contents.

Images can be added to the book by placing them in the ``/book/_static/images``
directory. After committing, they will have a permalink assigned by GitHub.
You can then include the images in the notebook by referencing that permalink:

```
![](link-to-github-image-here)
```

Doing it this way ensures the images are still visible when the individual
pages are downloaded from the static website.

Example projects you can reference that use the JupyterBook format:

* https://byucamacholab.github.io/nonlinear-optics/
* https://byucamacholab.github.io/Photonics-Bootcamp/
