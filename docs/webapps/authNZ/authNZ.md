# Authentication and Authorization in Web Applications

There are two different ways to setup AuthNZ flow for a web application. 

## A SPA + backend API configuration would require 

Follow this [sample-js-react](https://github.com/okta/samples-js-react/tree/master) example from okta for the client side auth integration with okta, where the widget will be responsible for the signing via the okta auth flow and generate the access token in local storage if everything is good.

The `okta-hosted-login` is exactly what we are looking for. It will initiate the login to okta and obtain the access token for subsequent request to the backend services.

## A bundled monolithic application

This will bundle both frontend and backend as a single application. And use the same server to host both backend API and frontend web ui. This is typically how traditional web applications work(PHP/rails/JSP/etc.).


## Resources

- [OKTA: Add user authentication to your React app](https://developer.okta.com/code/react/)
- [Implementing Okta Authentication In React](https://www.smashingmagazine.com/2022/08/implementing-okta-authentication-react/)
- FASTAPI Integration
	- [Build and Secure an API in Python with FastAPI](https://developer.okta.com/blog/2020/12/17/build-and-secure-an-api-in-python-with-fastapi)
	  - [github repo: okta-fastapi](https://github.com/oktadev/okta-fastapi/blob/d3f7784cc4eff758b4caca662a03f4e24d184aae/main.py#L54-L91)
	- [Python FastAPI microservice with Okta and OPA](https://www.stackstalk.com/2021/12/python-fastapi-with-okta.html)



