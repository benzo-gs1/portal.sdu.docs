# Curriculum 📅

```js
{
  _id: ObjectId('some-id'),
  semesters: [
    {
      index: 1,
      courses: [
        {
          _id: ObjectId('some-course-1')
        },
        {
          _id: ObjectId('some-course-2')
        }
      ],
      electives: [
        [ // elective group
          {
            _id: ObjectId('some-course-3')
          },
          {
            _id: ObjectId('some-course-4')
          }
        ],
        [ // elective group
          {
            _id: ObjectId('some-course-5')
          },
          {
            _id: ObjectId('some-course-6')
          }
        ],
      ]
    }
  ],
  year: 2020,
  code: 10113,
  cipher: "6B061001",
  title: {
    en: "Information Systems"
  },
  language: "en",
  department: {
    _id: ObjectId('some-id')
  },
  level: {
    short: "B",
    full: {
      en: "Bachelor"
    }
  }
}
```
