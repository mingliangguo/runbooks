# Generate SSL Key pairs for Https


## Steps to generate the key pairs

```bash
openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 366
```

After running the command above, it generates two files:

- cert.pem
- cert.pem

These files will be used for your app as a self-signed key pairs.

For example, a python FASTAPI service can use the self-signed certs as following(assuming the path is correct):

```python
if __name__ == "__main__":
    uvicorn.run("main:app", reload=True, port=8000, host="0.0.0.0", ssl_keyfile="./certs/key.pem",
                ssl_certfile="./certs/cert.pem")
```


