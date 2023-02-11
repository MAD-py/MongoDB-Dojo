# **MongoDB** Shell

**MongoDB** shell allows you to connect to MongoDB or MongoDB Atlas to work with the data directly from a terminal and to ease the database configuration process.

## CRUD with **MongoDB** Shell

To test the shell we will assume that you want to store an inventory in a *collection* named "inventory".

### Create Documents:

\
Inserting a single document can be done with:
```bash
db.inventory.insertOne(
    {
        item: "canvas",
        qty: 100,
        tags: ["cotton"],
        size: {h: 28, w: 35.5, uom: "cm"}
    }
)
```

Inserting multiple documents can be done with:
```bash
db.inventory.insertMany([
    {
        item: "journal",
        qty: 25,
        tags: ["blank", "red"],
        size: {h: 14, w: 21, uom: "cm"}
    },
    {
        item: "mat",
        qty: 85,
        tags: ["gray"],
        size: {h: 27.9, w: 35.5, uom: "cm"}
    },
    {
        item: "mousepad",
        qty: 25,
        tags: ["gel", "blue"],
        size: {h: 19, w: 22.85, uom: "cm"}
    }
])
```

## Read Documents:

\
Selecting all documents can be done with:
```bash
db.inventory.find({})
```

Selecting multiple documents using filters can be done with:
```bash
db.inventory.find({qty: {$lt: 30}})
```

MongoDB allows you to create conditions as complex as you want to create filters to select, update or delete documents, these conditions can be created with logical operators such as *AND*, *OR*, *lt*, *gt*, among many other.

If you want to find out what other types of operators can be used in MongoDB queries you are invited to check the following [link](https://www.mongodb.com/docs/manual/reference/operator/query/).

## Update Documents:

\
Updating a single document can be done with:
```bash
db.inventory.updateOne(
    {item: "journal"},
    {$set: {"size.w": 22, qty: 30}}
)
```

Updating multiple documents can be done with:
```bash
db.inventory.updateMany(
    {qty: {$lt: 50}},
    {$set: {"size.uom": "in"}}
)
```

The `$set` operator in all examples is used to command which values you want to update.

## Delete Documents:

\
Deleting a single document can be done with:
```bash
db.inventory.deleteOne({item: "mat"})
```

Deleting all documents can be done with:
```bash
db.inventory.deleteMany({})
```

Deleting multiple documents using filters can be done with:
```bash
db.inventory.deleteMany({qty: {$gt: 30}})

```
