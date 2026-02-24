# MongoDB Operations: A Comprehensive Guide

![MongoDB Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/0/00/Mongodb.png/1280px-Mongodb.png?20180423182709)

A collection of MongoDB scripts to demonstrate various operations with MongoDB. This repository covers setup, reading, updating, deleting, aggregation, indexing, and administrative commands.

---

## Table of Contents

- [Setup and Insert Data](#setup-and-insert-data)
- [Reading Data](#reading-data)
- [Updating Documents](#updating-documents)
- [Deleting Documents](#deleting-documents)
- [Aggregation Examples](#aggregation-examples)
- [Indexing and Performance](#indexing-and-performance)
- [Admin Commands](#admin-commands)
- [Contact Information](#contact-information)
- [License](#license)
- [Folder Structure](#folder-structure)

---

## Setup and Insert Data

- Initialize the database and insert sample data.
- Script: `01_setup.mongodb.js`

### Example:

```js
// Connect to MongoDB
const { MongoClient } = require("mongodb");
const url = "mongodb://localhost:27017";
const client = new MongoClient(url);

async function run() {
  try {
    await client.connect();
    console.log("Connected to MongoDB!");
    const db = client.db("ecommerce");
    const products = db.collection("products");
    // More setup code...
  } finally {
    await client.close();
  }
}

run().catch(console.error);
```

---

## Reading Data

- Find all documents and pretty print them.
- Filter data using queries.
- Script: `02_reading.mongodb.js`

### Example:

```js
db.products.find();
db.products.find().pretty();
```

---

## Updating Documents

- Update single and multiple documents.
- Script: `03_update.mongodb.js`

### Example:

```js
db.products.updateOne({ name: "Wireless Mouse" }, { $set: { price: 899 } });
```

---

## Deleting Documents

- Delete individual and multiple documents.
- Script: `04_delete.mongodb.js`

### Example:

```js
db.contacts.deleteOne({ name: "Alice" });
```

---

## Aggregation Examples

- Perform aggregation operations like `$match`, `$group`, and `$sort`.
- Script: `05_aggregation.mongodb.js`

### Example:

```js
db.orders.aggregate([{ $group: { _id: "$status", totalOrders: { $sum: 1 } } }]);
```

---

## Indexing and Performance

- Create and manage indexes for better performance.
- Script: `06_indexes.mongodb.js`

### Example:

```js
db.products.createIndex({ name: 1 });
```

---

## Admin Commands

- Useful commands for managing the database.
- Script: `07_AdminCommands.mogodb.js`

### Example:

```js
db.stats();
db.serverStatus();
```

---

## Contact Information

For any inquiries, suggestions, or feedback, please contact the repository maintainer:

- **Email**: asphaltshubhuu@gmail.com
- **LinkedIn**: [Shubham Raut](https://www.linkedin.com/in/shubham-raut-865a21203)
- **GitHub**: [SRCarlo](https://github.com/SRCarlo)

---

## License

This repository is licensed under the MIT License. See the LICENSE file for more details.

---

## Authors

- **Shubham Raut** – _Initial work_ – [SRCarlo](https://github.com/SRCarlo) – [MongoDB-Magic](https://github.com/SRCarlo/MongoDB-Magic)

---

## Clone the Repository

To clone the repository, run the following command:

```bash
git clone https://github.com/SRCarlo/MongoDB-Magic.git
```

---

## Folder Structure

Here’s the structure of the repository:

```
MONGODB/
│
├── 01_setup.mongodb.js     # Database setup and insertion scripts
├── 02_reading.mongodb.js   # Reading data from MongoDB
├── 03_update.mongodb.js    # Update documents in MongoDB
├── 04_delete.mongodb.js    # Deleting documents
├── 05_aggregation.mongodb.js  # Aggregation operations
├── 06_indexes.mongodb.js   # Indexing and performance
├── 07_AdminCommands.mongodb.js  # Useful admin commands
├── MongoDB Handbook.pdf    # MongoDB HandBook
└── README.md               # This README file

```

---

## License

MIT License

Copyright (c) [2026] SRCarlo

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
