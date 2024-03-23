# AuthN/Z integration


## Okta integration

- [okta cli](https://cli.okta.com/)

### Install okta cli on MacOS

```bash
brew install --cask oktadeveloper/tap/okta
```

Setup a okta developer account(if not having one)

```bash
okta register
okta login
okta apps create
```

Once the okta app is created, the issuer, client ID, and client secret will be stored in an `.okta.env` file in your current directory.





