# GCP Auth


## Login with GCP CLI And set quota project

```bash
gcloud auth application-default login
gcloud auth application-default set-quota-project my-awesome-project
```

You need to authenticate with GCP first before setting the quota project.


## Sample code for GCP Auth

### Reference:

- [google-auth](https://googleapis.dev/python/google-auth/latest/user-guide.html#credentials-and-account-types)
- [google-auth-library-python: test_credentials.py](https://github.com/googleapis/google-auth-library-python/blob/e216b9e9a431c6892ef5fbaee436ea2a02695de7/tests/oauth2/test_credentials.py#L774-L788)

### Sample code

```python
import google.auth
import google.cloud.bigquery as bq

# with default auth config
creds, project = google.auth.default()

# if need to specify application specific scopes
creds, project = google.auth.default(
    scopes=['https://www.googleapis.com/auth/cloud-platform'])

# to obtain a bigquery client with quota project
# option 1
c = creds.with_quota_project(quota_project)
client = bq.client.Client(credentials=c)

# option 2
client = bq.client.Client(
    credentials=creds, client_options={"quota_project_id": quota_project}
)
client.query("SELECT 1").result().to_dataframe()

```
