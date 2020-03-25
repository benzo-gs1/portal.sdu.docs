# Users model 🙍‍♂️

```js
{
  username: {
    type: String,
    required: true,
    unique: true,
    lowercase: true
  },
  password: {
    type: String,
    required: true
  },
  role: {
    type: String,
    required: true
  },
  language: {
    type: String,
    default: "en"
  }
}
```
