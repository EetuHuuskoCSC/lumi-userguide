# LUMI Docs

This repository contains master data for the [LUMI documentation][1] which
is in sync with 'production' branch. This documentation is written in Markdown which
is converted to HTML/CSS/JS with the mkdocs static site generator. The
documentation is themed with mkdocs-material + LUMI customization.

[1]: https://docs.lumi-supercomputer.eu

- [Create Issue](#creating-issues)
- [Building](#building)
  - [Edit with live preview](#edit-with-live-preview)
  - [Build a Docker Image](#build-a-docker-image) 
  - [Generate the static site](#generate-the-static-site)


## Creating issues

If you find that anything is wrong, badly written or missing, please
help us to fix it. We try to make this guide as good as possible. We
appreciate your help.

The easiest way to create issues is to go to a page that you want to
create an issue about, and click 'File a bug report for this article'. More
general issues can be submitted through GitHubs [Issues tab][2].

Creating an Issue requires a GitHub account.

[2]: https://github.com/Lumi-supercomputer/docs/issues

## Building

The first step to build a local copy of the LUMI documentation is to clone
the git repository.

```
git clone git@github.com:Lumi-supercomputer/lumi-userguide.git
cd lumi-userguide
```

The next step is to set up your environment by creating a python virtual
environment and to activate it.

```
python3 -m venv venv
source venv/bin/activate
```

Once the virtual environment is ready, you can install the needed
dependencies.

```
pip install -r requirements.txt
```

### Edit with live preview

With the appropriate python environment activated, go to the root
directory of the repository (where the `mkdocs.yml` file is located) and run

```
mkdocs serve
```

This command will start a live-reloading local web server that can be accessed
in a web browser via: http://127.0.0.1:8000. The local web serve will 
automatically re-render and reload the site when you edit the documentation.

### Build a Docker Image

You can also create a Docker container to host the docs. First build
an image from the included Dockerfile.

```
sudo docker build -t lumi-user-guide .
```

This will build a container image called `lumi-user-guide`. Once the
image is built, you can run it.

```
docker run --rm -it -p 80:8000 --name lumi-user-guide lumi-user-guide
```

This will run a web server on your computer. You can view the content of the 
user guide by pointing your browser to
[localhost][3].

[3]: http://localhost

### Generate the static site

To build a self-contained directory containing the full website run:

```
mkdocs build
```

The generated files will be located in the `site/` directory.
