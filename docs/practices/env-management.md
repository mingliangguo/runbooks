# Environment variable management


## Env files

this file is an example file of `.env`, `.env` is a common file used to source environment variables. It's supported by various tools. The file itself is usually not checked into source control system. The common practice is to create a `.env` file locally and update with actual values. If you run the service in pycharm, you can use this [envfile plugin](https://plugins.jetbrains.com/plugin/7861-envfile) to load the env .

Or if you intend to start the service from cli, you can try:

```bash
set -a; source .env; set +a
```
so you don't have to create a separate script to source the env file.
```
