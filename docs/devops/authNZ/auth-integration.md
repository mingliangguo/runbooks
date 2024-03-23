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

## OAUTH integration options

### SPA with OKTA

See docs from the official website: [How Authentication and Authorization Work for SPAs](https://developer.okta.com/blog/2023/04/04/spa-auth-tokens)


## OKTA Auth related URLs


- well-known url: {Issuer}/.well-known/openid-configuration


