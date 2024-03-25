# Authentication and Authorization in Web Applications

There are two different ways to setup AuthNZ flow for a web application. 

A SPA + backend API configuration would require 

Follow this [sample-js-react](https://github.com/okta/samples-js-react/tree/master) example from okta for the client side auth integration with okta, where the widget will be responsible for the signing via the okta auth flow and generate the access token in local storage if everything is good.

The `okta-hosted-login` is exactly what we are looking for. It will initiate the login to okta and obtain the access token for subsequent request to the backend services.


