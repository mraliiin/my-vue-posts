# Basic CRUD with Vue.js and Node

This example app shows how to create a Node.js API and display its data with a Vue.js UI.

```bash
npm install
```

To run the server:
```bash
node ./src/server
```

To run the client:

```bash
npm run dev
```

### Create an Application in Okta

You will need to [create an OpenID Connect Application in Okta]

#### Server Configuration

Set the `issuer` and copy the `clientId` into `src/server.js`.

```javascript
const oktaJwtVerifier = new OktaJwtVerifier({
  clientId: '{client_id}',
  issuer: 'https://{okta_domain}.com/oauth2/default'
})
```

#### Client Configuration

Set the `issuer` and copy the `clientId` into `src/router/index.js`.

```javascript
Vue.use(Auth, {
  issuer: 'https://{okta_domain}.com/oauth2/default',
  client_id: '{client_id}',
  redirect_uri: 'http://localhost:8080/implicit/callback',
  scope: 'openid profile email'
})
```

## License

Apache 2.0, see [LICENSE](LICENSE).
