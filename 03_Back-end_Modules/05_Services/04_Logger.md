# Logger ✍️

```js
class Logger {}
```

- **closeServer** - kills the given server

## closeServer()

```js
const app = express(); // Express application
const server = app.listen(PORT); // returns server

ServerService.closeServer(server); // server is killed
```
