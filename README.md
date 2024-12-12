# LibraryOfCRUD

🎉 **Welcome to LibraryOfCRUD** 🎉  
A comprehensive guide to mastering MongoDB CRUD operations with clear examples and advanced query techniques. Perfect for beginners and professionals alike!

---

## 📖 Table of Contents

- [About](#about)
- [Features](#features)
- [Commands Overview](#commands-overview)
- [Usage Examples](#usage-examples)
  - [Create Operation](#create-operation)
  - [Read Operation](#read-operation)
  - [Update Operation](#update-operation)
  - [Delete Operation](#delete-operation)
  - [Advanced Query](#advanced-query)

---

## 📚 About

**LibraryOfCRUD** is a step-by-step guide designed to teach MongoDB CRUD operations (Create, Read, Update, Delete) effectively. It includes practical examples and advanced query techniques to help you build and manage robust databases.

---

## 🌟 Features

- ✅ Easy-to-follow MongoDB commands
- ✅ Real-world use cases and examples
- ✅ Advanced query techniques
- ✅ Beginner-friendly yet detailed
- ✅ Markdown formatting for readability

---

## 💻 Commands Overview

| Operation | Command Description                     | Example Command                          |
|-----------|-----------------------------------------|------------------------------------------|
| **Create** | Insert a document                      | `db.collection.insert()`                |
| **Read**   | Retrieve documents                     | `db.collection.find()`                  |
| **Update** | Modify fields in documents             | `db.collection.update()`                |
| **Delete** | Remove documents from a collection     | `db.collection.remove()`                |

---

## 🛠️ Usage Examples

### 📂 Create Operation

1. **Switch to a new database named `library`:**
   ```shell
   use library
   ```

2. **Create a collection named `books` (optional):**
   ```shell
   db.createCollection("books")
   ```

3. **Insert a document into the `books` collection:**
   ```shell
   db.books.insert({
     title: "The Great Gatsby",
     author: "F. Scott Fitzgerald",
     published_year: 1925
   })
   ```

---

### 🔍 Read Operation

1. **Retrieve all documents:**
   ```shell
   db.books.find()
   ```

2. **Find all books by `J.K. Rowling`:**
   ```shell
   db.books.find({ author: "J.K. Rowling" })
   ```

3. **Find the earliest published book:**
   ```shell
   db.books.find().sort({ published_year: 1 }).limit(1)
   ```

---

### ✏️ Update Operation

1. **Update the published year of `The Catcher in the Rye` to 2024:**
   ```shell
   db.books.update(
     { title: "The Catcher in the Rye" },
     { $set: { published_year: 2024 } }
   )
   ```

2. **Add a new field `genre` with the value `Mystery` to all books:**
   ```shell
   db.books.update(
     {},
     { $set: { genre: "Mystery" } },
     { multi: true }
   )
   ```

---

### 🗑️ Delete Operation

1. **Remove the book `1984`:**
   ```shell
   db.books.remove({ title: "1984" })
   ```

2. **Delete books published before the year 2000:**
   ```shell
   db.books.remove({ published_year: { $lt: 2000 } })
   ```

---

### 🚀 Advanced Query

1. **Find the top 3 recently published books:**
   ```shell
   db.books.find().sort({ published_year: -1 }).limit(3)
   ```

2. **Retrieve books where the title contains `MongoDB` or `NoSQL`:**
   ```shell
   db.books.find({ title: { $regex: /(MongoDB|NoSQL)/i } })
   ```

---

## 🚀 Let's Build Together!
