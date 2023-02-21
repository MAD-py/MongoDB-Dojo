# Practical Example

In this dojo we will explore how to implement a basic CRUD with Python, Nodejs, go and from the **MongoDB** shell. For this we are going to simulate an online course platform that requires to have a list of available courses and another list with users with all the courses they have completed and all the courses they have started.

## Entities

Entities in **MongoDB** can be understood as collections since one always seeks to store documents with a similar meaning in the same collection, for this example we will use two entities which are the courses of the platform and the users.

### Course

This collection will have as base the following fields (remember that **MongoDB** is NoSQL and not all the documents of a collection have to have the same fields).

```json
{
    "_id": ObjectId("612d1e835ebee16872a109a4"),
    "name": "Cloud Computing I",
    "instructor": {
        "name": "Jose Gomez Gomez",
        "email": "josegg@gmail.com"
    },
    "price": "$45.78",
    "certifies": true
}
```

Some of the courses will have an extra field that refers to a second instructor in the course, this field will be called "*co_instructor*" and will be the same as the "*instructor*" field.

```json
{
    "_id": ObjectId("800d1e735ufuue16122a001t1"),
    "name": "Cloud Computing II",
    "instructor": {
        "name": "Jose Gomez Gomez",
        "email": "josegg@gmail.com"
    },
    "co_instructor": {
        "name": "Juan Zapata Gomez",
        "email": "jzg@gmail.com"
    },
    "price": "$38.00",
    "certifies": true
}
```

## User

This collection will have references to course collection and base information.

```json
{
    "_id": ObjectId("642d1e835ebff16872b239a4"),
    "name": "Emanuel",
    "last_name": "Rojas Moreno",
    "emails": [
        {
            "email": "emanuel.rojas@gmail.com",
            "type": "academic",
        },
        {
            "email": "ema123@gmail.com",
            "type": "personal",
        }
    ],
    "courses": {
        "completed": [
            ObjectId("612d1e835ebee16872a109a4"),
            ObjectId("732d1e835fgff12172a199a4")
        ],
        "started": [ObjectId("f783k1e825eboe16872a203b3")]
    }
}
```
*Note: "ObjectId" are internal objects used by MongoDB, these values are usually UUIDs so that they are unique and can be used to uniquely identify a document.*
