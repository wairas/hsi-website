# his-website
Website for the Hyper-spectral Imaging Group at the University of Waikato.

## Content

The content for the website lives in the [docs](docs) sub-folder and consists
of [Markdown](https://github.github.com/gfm/) text files. These files need
to have the extension `.md`.

**NB:** Any modifications or additions that get committed via the web interface
automatically trigger a rebuild of the site via Github Actions (see 
[Deploying](#deploying)).

## Modifying

Simply edit the respective page in the web-browser (you need to be logged in 
into github and be a member of the contributors team). You can do that either
through the *pen* icon on the web page itself or go to this repo and navigate
to the correct `.md` file and then click on the *pen* icon there.

## Adding

Adding a page consists of two steps:

* create a new `.md` file in the [docs](docs) sub-folder (the file name should 
  be all lower-case and contain no spaces - use underscores instead)
* add this `.md` file in the [mkdocs.yml](mkdocs.yml) configuration file
  under the `nav` section with a suitable title (the title can contain spaces 
  and doesn't have to be all lower-case).
  

## Local

### Installation

```bash
python3 -m venv venv
./venv/bin/pip install mkdocs==1.4.2 mkdocs-video==1.3.0 jinja2==3.1.2 "Markdown<3.4.0" mkdocs-table-reader-plugin==1.1.0 mkdocs-material==8.5.10
```

### Serving

```bash
./venv/bin/mkdocs serve
```

## Deploying

Any push will trigger a rebuild of the site on github via github actions:

[.github/workflows/main.yml](.github/workflows/main.yml)
