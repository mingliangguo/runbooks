# Auth CLI


```bash
curl -D 'https://dev-xyz.okta.com/oauth2/v1/token' \
-H 'Authorization: Basic base64-encoded-client_id:client_secret' \
-H 'content-type: application/x-www-form-urlencoded' \
-d 'grant_type=authorization_code' \
-d 'redirect_uri=http://localhost:3000' \
-d 'code=auth_code'
```

