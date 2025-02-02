### AWS JWT (json web token)
- used for authenticating based on a trusted external identity provider 
- used for [[AWS STS (security token service)]] when assuming a role with web token
- encoded json containing information about the issuer the audience and other information

```
import jwt

web_identity_token = "eyJhbGciO..."

jwt.decode(web_identity_token, options={"verify_signature": False})

{'aud': ['[sts.amazonaws.com](http://sts.amazonaws.com)'],
'exp': 1738229015,
'iat': 1738142615,
'iss': '[[https://oidc.eks.eu-central-1.amazonaws.com/id/14187A24BB02EE90F1221E2B321D1728]...
}
```

