# FastAPI HOWTO

## How to only protect a (or some) specific routes

This [issue](https://github.com/tiangolo/fastapi/discussions/9827) discussed the pros/cons between using middleware and dependencies.


```python
app = FastAPI()

app.add_middleware(
    OAuth2Middleware,
    public_key=AuthService().get_public_key()
)

# example 1 => middleware
@app.get('/test_1')
def test():
    return {'message': 'it works'}

# example 2 => Depends
@app.get('/test_2')
def test(user = Depends(__auth_service.get_current_user)):
    return {'message': 'it works'}


# example 3 => sub router
app.include_router(
    secured.router,
    dependencies=[Depends(AuthService().get_current_user)]
)

# example 3.1 => a variation of exmaple 3, using a sub-route for secured routes

def check_authentication(self, request: Request, token: HTTPAuthorizationCredentials = Security(HTTPBearer())):
        user = get_current_user(token) # function to decode and validate token
        request.scope["user"] = user # token added to request.scope (similar to an AuthenticationMiddleware)


app.include_router(
    secured.router,
    dependencies=[Depends(check_authentication)]
)

# example 4 => static folder
app.mount("/static", StaticFiles(directory="static"), name="static")
```

## Implement a basic health check endpoint

- [gist example](https://gist.github.com/Jarmos-san/0b655a3f75b698833188922b714562e5)

## How to disable access logs for certain endpoints(/health)

- check this github [issue](https://github.com/encode/starlette/issues/864)
