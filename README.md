# Readme

My own runbook collections.


`Make it work, make it right, make it fast. In that order. - by Kent Beck`


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
