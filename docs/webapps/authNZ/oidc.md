# OIDC

OpenID Connect (OIDC), which is an identity layer on top of the OAuth 2.0 protocol, there are two primary types of login flows: IdP-initiated (Identity Provider initiated) and SP-initiated (Service Provider initiated). These refer to the entity that initiates the authentication process.

## SP-Initiated (Service Provider Initiated) Login:

- Initiation: This flow begins at the Service Provider (SP). A common example is a user trying to access a protected resource or service and being redirected to the login page.
- Process:
	- The user attempts to access a resource on the SP.
	- The SP, recognizing that the user is not authenticated, redirects the user to the Identity Provider (IdP) with an authentication request.
	- The user authenticates with the IdP (e.g., by entering username and password).
- Post authentication, the IdP sends an authentication response to the SP (usually an ID token and an access token).
	- The SP validates the response and grants access to the user.
- Advantages: It’s more secure as it can prevent certain types of attacks (like unsolicited login attempts) and is generally the preferred method for initiating single sign-on (SSO) in enterprise settings.

## IdP-Initiated (Identity Provider Initiated) Login:

- Initiation: This flow begins at the IdP. It is used in scenarios where a user is already authenticated with the IdP and wants to access a service or application (SP) without additional login steps.
- Process:
	- The user is logged in to the IdP and selects a service to access from a provided list (or is automatically directed to a service upon logging in to the IdP).
	- The IdP creates an authentication response (like an ID token or SAML assertion) and sends it directly to the SP.
	- The SP, which receives the assertion from the IdP, validates it and grants access to the user.
- Advantages: It offers convenience for users who are already authenticated and want seamless access to multiple services. It’s commonly used in scenarios where an organization has a central portal through which users can access multiple applications.

## Security Considerations:

SP-Initiated Flow: More secure as it ensures the user is going to the intended service provider, reducing the risk of phishing or man-in-the-middle attacks.
IdP-Initiated Flow: Can be less secure as it could be vulnerable to certain attacks if not implemented correctly. However, it is still widely used, especially in environments where the IdP is trusted and secure.
The choice between IdP-initiated and SP-initiated flows often depends on the specific requirements and security considerations of the organization implementing OIDC.
