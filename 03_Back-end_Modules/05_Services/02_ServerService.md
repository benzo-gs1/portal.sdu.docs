# Server Service 🖥️

```js
class ServerService {
  static closeServer(server);
}
```

- **closeServer** - kills the given server

## closeServer()

```js
const app = express(); // Express application
const server = app.listen(PORT); // returns server

ServerService.closeServer(server); // server is killed
```
