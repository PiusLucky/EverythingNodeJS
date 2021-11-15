# EverythingNodeJS
hmm... just some images and pdfs, including links explaining Authorization and Authentication in a typical NodeJS Application.

## Check Branches
You can check the branches above for the different sections.

# Using JWT
https://jwt.io/introduction
## How do JSON Web Tokens work?
In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned. Since tokens are credentials, great care must be taken to prevent security issues. In general, you should not keep tokens longer than required.

You also should not store sensitive session data in browser storage due to lack of security.

Whenever the user wants to access a protected route or resource, the user agent should send the JWT, typically in the Authorization header using the Bearer schema. The content of the header should look like the following:

```shell
Authorization: Bearer <token>
```

This can be, in certain cases, a stateless authorization mechanism. The server's protected routes will check for a valid JWT in the Authorization header, and if it's present, the user will be allowed to access protected resources. If the JWT contains the necessary data, the need to query the database for certain operations may be reduced, though this may not always be the case.

If the token is sent in the Authorization header, Cross-Origin Resource Sharing (CORS) won't be an issue as it doesn't use cookies.

The following diagram shows how a JWT is obtained and used to access APIs or resources:

![image](https://user-images.githubusercontent.com/32282934/141715317-27db973d-d077-4ebd-84b5-0b47292ada66.png)


1. The application or client requests authorization to the authorization server. This is performed through one of the different authorization flows. For example, a typical OpenID Connect compliant web application will go through the /oauth/authorize endpoint using the authorization code flow.

2. When the authorization is granted, the authorization server returns an access token to the application.

3. The application uses the access token to access a protected resource (like an API).


Do note that with signed tokens, all the information contained within the token is exposed to users or other parties, even though they are unable to change it. This means you should not put secret information within the token.


