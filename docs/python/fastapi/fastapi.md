# FASTAPI


## Useful links

- [swagger](http://localhost:8000/docs)
- [enable https](../../../devops/ssl/generate_ssl_key_pairs)


## Auth integration with Okta

## Validate tokens using jws

There are two ways to validate the jwt tokens from a web application:
- use jws uri to fetch the jwt keyset and use it for the validation
	- with this approach, the jws only needs to be fetched once and then uses locally.
- invoke the [okta introspect](https://developer.okta.com/docs/reference/api/oidc/#introspect) : `$(baseUrl}/v1/introspect` endpoint if it's provided by the oauth provider and validate the token remotely.

This article - [Build and Secure an API in Python with FastAPI](https://developer.okta.com/blog/2020/12/17/build-and-secure-an-api-in-python-with-fastapi) provides an example of both approaches.
