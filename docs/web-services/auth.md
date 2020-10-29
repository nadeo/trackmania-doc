# Auth

Authentication is available through OAuth2. 

## Auth code flow

1. Redirect the user to https://api.trackmania.com/oauth/authorize with the query parameters:
    - `response_type`: `code`
    - `client_id`: the client ID you created in the manager
    - `scope`: space separated value of scopes
    - `redirect_uri`: one of the redirect URIs in the application you created in the manager
    - `state`: a non predictable random string. You should store this value and check if the value is the same at later stage.
2. After the user authorize your application, they are redirected to the `redirect_uri` with the query parameter:
    - `code`: a code you need to exchange for an access token
    - `state`: check that it's the same value than then one you generated at step 1.
3. The application should issue a `POST` request to https://api.trackmania.com/oauth/access_token with the parameters:
    - `grant_type`: `authorization_code`
    - `client_id`: your client ID
    - `client_secret`: your client secret
    - `code`: the code from stage 2
    - `redirect_uri`: from stage 1

The answer of stage 3 will contain:

   - `token_type`
   - `expires_in`
   - `access_token`
   - `refresh_token`
