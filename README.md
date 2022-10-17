# Template documentation

This repository contains a template for Read The Docs style auto documentation
generation using [Sphinx](https://www.sphinx-doc.org/en/master/).

## Usage

Copy and paste `docs` directory and `.github/workflows/pages.yaml` file.
`docs` directory contains necessary minimum confiuration files for Sphinx builder.
The github `pages` workflow automatically updates the webpage after a push to the `master` or the `main` branch.
Include the contents of the `.gitignore` file in your own `.gitignore` file.

```{note}
Make sure not to copy `LICENSE` and `README.md` files since license and readme for the documented project high likely to be different.
```

## Populating and the documentation

### Installation
[Sphinx](https://www.sphinx-doc.org/en/master/) is a Python based documentation generator.
This template requires packages described in the `docs/requirements.txt` to be installed.

First install python3 and `pip` command line python package installer if ther are not installed already.
```bash
sudo apt install python3 python3-pip
```

```{note}
In some cases it maybe preferable to install python3 using `sudo apt install python-is-python3`.
```

Install required packages
```bash
pip install -r ./docs/requirements.txt
```

### Building

Navigate inside the `docs` directory and execute the command below.

```bash
cd docs
sphinx-build -b html . _build
```

```{note}
Check your [.gitignore](https://www.atlassian.com/git/tutorials/saving-changes/gitignore) file and make sure `_build` directory is ignored.
When the repository is pushed to github, sphinx builder will be executed on the server.
```

You have several options to test out the generated documentation.
First, you may just navigate into `_build` directory and open it with your _favorite_ internet browser.
Second, you may run a simple http server via `python -m http.server 8080 -d docs/_build`
and explore it by visiting [http://localhost:8080](http://localhost:8080).

## Deployment

For more information, [read Github's take on github pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

1. Visit the repository on github.

2. Navigate to the repository settings.
![img](https://docs.github.com/assets/cb-27528/images/help/repository/repo-actions-settings.png)

3. In the "Code and automation" section of the sidebar, click  Pages.Find "Pages" on the left navigation panel.

4. Under "Build and deployment", under "Source", select Deploy from a branch.

5. Select `gh-pages` branch.

6. It should be all set. The documentation will be hosted at `https://<organization_name>.github.io/<repository_name>`


```{note}
The is a way to use custom URLs. If you are interested in it, please refer to [github's take on that issue](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
```

## Documentation Syntax

You can add as much as readme files inside the `docs/index.md` file.
The files can be `.md` or `.rst`.
If you plan to use `.md` files, sphinx special syntax documentation is hosted at [MyST](https://myst-parser.readthedocs.io/en/latest/syntax/syntax.html) documentation.
