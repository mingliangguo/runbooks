# My Own Runbooks

Use this to capture some useful notes during my day-to-day work.

It's created with [mkdocs.org](https://www.mkdocs.org), visit the website to see more details of it.

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


## Setup

```bash
mkdocs new runbooks
mkdocs get-deps
pip install mkdocs-material
mkdocs serve
```

After the server starts, you can access the docs via http://localhost:8000


## Deploy as github pages

Refer to [mkdocs: deploy your docs](https://www.mkdocs.org/user-guide/deploying-your-docs/)

```bash
# run this at the root of the repo
mkdocs gh-deploy 
```

After it's done, you can access the webiste with [github-page/runbooks](https://mingliangguo.github.io/runbooks), or with other configurations: [mingliang.me/runbooks](https://mingliang.me/runbooks).


## References

Here I collected some very nice frontend repositories from internet(github):

- [Frontend for home assistant](https://github.com/home-assistant/frontendb)
