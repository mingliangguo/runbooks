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
- request userinfo: https://{okta_dev_account}.okta.com/oauth2/default/v1/userinfo


CURL commands:

```bash
export JWT=your_access_token
curl -H "Authorization: Bearer ${JWT}" https://${okta_dev_domain}.okta.com/oauth2/default/v1/userinfo
# get user details
curl -v -H "Authorization: Bearer ${JWT}"  https://${okta_dev_domain}.okta.com/api/v1/users
```

## Okta token refresh

- [React Okta SDK not making refresh token call automatically](https://devforum.okta.com/t/react-okta-sdk-not-making-refresh-token-call-automatically/25433)
  - this link provides the screenshot about okta app setup.


## Return user groups in OKTA OAuth flow

According to this [No ‘groups’ scope in the console for the default Authorisation Server](https://devforum.okta.com/t/no-groups-scope-in-the-console-for-the-default-authorisation-server/5573)

By default, Okta doesn't have a `groups` scope defined, in order to use it and have users' group information returned in the token, you need to define both a scope and a claim for it. Here is the brief steps:

- In the authorization server, define a scope named `groups`, and toggle the option - `Include in public metadata`.
- Add a claim named `groups`, and make it include in `access token`, and set the filter as `matches regex` with value `.*`, and `Include in` the `groups` scope.

## How okta-react handles the /login/callback request?

In an OAuth flow, when the users finish the authentication flow configured with the oauth provider (here okta), the auth provider will send the request back to the originally configured callback url, i.e. `/login/callback`. This route is typically mapped to [okta-react/src/LoginCallback.tsx](https://github.com/okta/okta-react/blob/master/src/LoginCallback.tsx). It could be a bit confusing how it works. As it is a purely client-side component, how it's possible to handle the redirect? Actually this is quite a standard implementation in a SPA(single page application) context, where any non-existing URLs are mapped to the default home page (e.g. `/` or `/index.html`, etc.), in the default landing page, it has the logic to handle client side routing, where the `/login/callback` should have been registered to the okta's `LoginCallback` component.
