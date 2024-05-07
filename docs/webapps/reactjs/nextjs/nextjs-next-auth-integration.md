# NextAuth with NextJS


There is a sample application in the [NextAuth](https://github.com/nextauthjs/next-auth/tree/main/apps/examples/nextjs) github repository. It's a bit out-dated, but should be still helpful when needed. There is also a live demo of the sample app: [next-auth-example.vercel.app](https://next-auth-example.vercel.app/)

## Configuration Options

- https://next-auth.js.org/configuration/options

>  // Choose how you want to save the user session.
>  // The default is `"jwt"`, an encrypted JWT (JWE) stored in the session cookie.
>  // If you use an `adapter` however, we default it to `"database"` instead.
>  // You can still force a JWT session by explicitly defining `"jwt"`.
>  // When using `"database"`, the session cookie will only contain a `sessionToken` value,
>  // which is used to look up the session in the database.
>  strategy: "database",


## Troubleshooting


###  UntrustedHost: Host must be trusted. URL was: http://0.0.0.0:3000/auth/session. Read more at https://errors.authjs.dev#untrustedhost

When the auth flow is triggered, it throws an `UntrustedHost` error:
> UntrustedHost: Host must be trusted. URL was: http://0.0.0.0:3000/auth/session. Read more at https://errors.authjs.dev#untrustedhost

To fix it, for the time being, you need to expose `AUTH_TRUST_HOST` environment variable. This only happens in product build though.

```bash
AUTH_TRUST_HOST=http://localhost:3000
```


## Resources

- [How to use NextAuth.js for client-side authentication in Next.js](https://blog.logrocket.com/nextauth-js-client-side-authentication-next-js/)
- [Auth on the Next.js Edge Runtime with Auth.js (NextAuth 5) and MongoDB](https://blog.stackademic.com/authentication-and-authorization-on-the-edge-with-auth-js-nextauth-5-and-mongodb-5903d7e95f99)
