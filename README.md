# Phone Book and Messaging System

## Overview

This project implements a simple **Phone Book and Messaging System** using the Motoko programming language. The system provides functionality for storing phone book entries and maintaining a history of messages sent. The code is designed as an actor-based system, enabling asynchronous interactions and queries.

---

## Features

### Phone Book Management
- **Insert Phone Book Entry:** Add a new entry into the phone book with a name, phone number, and description.
- **Retrieve Phone Book Entry:** Query the phone book to retrieve an entry by name.

### Messaging System
- **Send Messages:** Send a message to a recipient, associating the message with the sender's phone number.
- **Retrieve Message History:** Query message history for a given sender's phone number.

---

## Data Structures

### Types
- **Name:** Represents the name of the contact (`Text`).
- **Phone:** Represents the phone number (`Text`).
- **Entry:** A record containing:
  - `desc` - A description of the contact (`Text`).
  - `phone` - The contact's phone number (`Phone`).
- **Message:** A record containing:
  - `receiver` - The recipient of the message (`Text`).
  - `mess` - The message content (`Text`).

### HashMaps
- **phoneBook:** A hash map to store phone book entries. Keys are `Name`, and values are `Entry`.
- **MessageHistory:** A hash map to store message history. Keys are `Phone` (sender's phone), and values are `Message`.

---

## Public Methods

### Phone Book Functions

#### `insert(name: Name, entry: Entry): async ()`
Adds a new entry to the phone book.

- **Parameters:**
  - `name` - The name of the contact.
  - `entry` - The phone book entry containing a description and phone number.
- **Usage:**
  ```motoko
  await actor.insert("John Doe", { desc = "Friend", phone = "123-456-7890" });
