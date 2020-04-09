# Users model 🙍‍♂️

```js
{
  _id: ObjectId('some-id'),
  username: "180101033",
  password: "some-password",
  roles: [
    {
      name: "Student",
      level: 0
    }
  ],
  language: "en",
  department: {
    _id: ObjectId('some-id'),
    name: "Computer Science"
  },
  faculty: {
    _id: ObjectId('some-id'),
    name: "Engineering and Natural Sciences"
  },
  curriculum: {
    _id: ObjectId('some-id')
  }
}
```
