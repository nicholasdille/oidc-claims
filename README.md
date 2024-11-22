# oidc-claims

Authenticates using OIDC and displays the claims from the ID token.

## Usage

Example usage:

```shell
oidc-claims \
    -auth-url https://gitlab.com/oauth/authorize \
    -token-url https://gitlab.com/oauth/token \
    -client-id CLIENT_ID \
    -client-secret CLIENT_SECRET \
    -scopes openid,profile,email \
    -local-server-port 8000
{
  "iss": "https://gitlab.com",
  "sub": "11",
  "aud": "[REDACTED]",
  "exp": 1732271262,
  "iat": 1732271142,
  "auth_time": 1732270319,
  "sub_legacy": "[REDACTED]",
  "name": "my_user",
  "nickname": "my_user",
  "preferred_username": "my_user",
  "email": "me@somewhere.io",
  "email_verified": true,
  "profile": "https://gitlab.com/my_user",
  "picture": "[REDACTED]",
  "groups_direct": [
    "group1",
    "group2"
  ]
}
```

By default, the underlying library uses a dynamic server port. By specifying `-local-server-port`, you can specify a fixed port which can be used in the redirect URI.

Add `-debug` to display messages from the underlying libraries.

## Installation

```shell
go install github.com/nicholasdille/oidc-claims
```
