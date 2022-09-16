# Auth

Authentication is available through OAuth2.

## Registration

You can register your application and get your credentials at [api.trackmania.com](https://api.trackmania.com).
After you created your application, make sure to save your `Identifier` (client ID) and `Secret` (client secret) for later.

## Grants

### Auth code flow

1. Redirect the user to https://api.trackmania.com/oauth/authorize with the following query parameters:
    - `response_type`: `code`
    - `client_id`: The client ID ("Identifier") you created in the manager.
    - `scope`: Space separated value of scopes. See [here](#scopes) for more information.
    - `redirect_uri`: One of the redirect URIs in the application you created in the manager.
    - `state`: A non predictable random string. You should store this value and check if the value is the same at later stage.
2. After the user authorized your application, they are redirected to the `redirect_uri` with these query parameters:
    - `code`: A code you need to exchange for an access token.
    - `state`: Check that this is the same value as the one you generated at step 1.
3. The application should now issue a `POST` request to https://api.trackmania.com/api/access_token with these parameters:
    - `grant_type`: `authorization_code`
    - `client_id`: Your client ID.
    - `client_secret`: Your client secret.
    - `code`: The code from stage 2.
    - `redirect_uri`: The redirect URI that was used in stage 1.

The answer of stage 3 will contain:

   - `token_type`: This determines how you'll use the token. `bearer` means you send it alongside your requests in the `Authorization` header with the format `Bearer <token>`.
   - `expires_in`: The number of seconds this token will remain valid.
   - `access_token`: The token you need to access the endpoints on `api.trackmania.com`.
   - `refresh_token`: The long-lived token you can use to refresh your access token once it runs out (see [here](#refresh-token-flow) for more information).

#### Refresh token flow

This lets you use a _refresh token_ to get a new access token - because it has a much longer lifetime than an access token, it's a useful shortcut to getting a new access token without having to go through the whole auth code flow again.

Simply send a `POST` request to https://api.trackmania.com/api/access_token with these parameters:
  - `grant_type`: `refresh_token`
  - `client_id`: Your client ID.
  - `client_secret`: Your client secret.
  - `refresh_token`: The refresh token from a previous request.
    
The endpoint will respond just like to the original `/access_token` request, and you'll get a new access token alongside a new refresh token for future requests.

### Client credentials

This is meant to be used for machine-to-machine authentication.
Note that this token will not be associated with a user, so not all `api.trackmania.com` endpoints might make sense in this scenario.

Issue a `POST` request to https://api.trackmania.com/api/access_token with the parameters:
  - `grant_type`: `client_credentials`
  - `client_id`: The client ID ("Identifier") you created in the manager.
  - `client_secret`: The client secret ("Secret") associated with your client ID.
  - `scope`: Space separated value of scopes. See [here](#scopes) for more information.

The answer will contain:

   - `token_type`: This determines how you'll use the token. `bearer` means you send it alongside your requests in the `Authorization` header with the format `Bearer <token>`.
   - `expires_in`: The number of seconds this token will remain valid.
   - `access_token`: The token you need to access the endpoints on `api.trackmania.com`.

### Implicit grant

As it's no longer a good practice, implicit grant won't be available.

## Scopes

There are several available scopes for some specific user-related endpoints. If you're using the [client credentials flow](#client-credentials), these scopes will have no effect since the token won't be associated with a user.

To see the required scopes for each endpoint, please refer to the [route documentation](https://api.trackmania.com/doc).
