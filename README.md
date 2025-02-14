# Microsoft Graph Email Backend for Django

An email backend for Django that uses Microsoft Graph to send and receive emails. It uses the `msal` library to retrieve an access token with Microsoft Graph and then uses the Microsoft Graph API to send and receive emails.

## Installation

To include it in your Django project, add it to your `INSTALLED_APPS` setting:

```python
INSTALLED_APPS = [
    ...
    'msgraph_email',
]
# or 
INSTALLED_APPS = INSTALLED_APPS + ('msgraph_email',)
```

Then add the following to your `settings.py` file:

```python
EMAIL_BACKEND = 'msgraph_email.MicrosoftGraphEmailBackend'
GRAPH_API_CREDENTIALS = {
    'client_id': 'your-client-id',
    'client_secret': 'your-client-secret',
    'tenant_id': 'your-tenant-id',
    'mail_from': 'your-email@your-domain.com' # to use Django's default email address, set this to os.getenv('DEFAULT_FROM_EMAIL')
}
```
