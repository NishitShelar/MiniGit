# MiniGit – Distributed Version Control System

MiniGit is a simplified implementation of a distributed version control system inspired by Git.
The goal of this project was to understand how Git works internally — from object storage to branching — and extend it with basic peer-to-peer synchronization.

---

## 🚀 Features

* **Content-addressable storage** using SHA-1 hashing
* **Git object model**:

  * Blob (file data)
  * Tree (directory structure)
  * Commit (history + metadata)
* **Staging area (index)** for tracking changes
* **Branching and checkout support**
* **Commit history (log)**
* **Status tracking** (staged, unstaged, untracked, deleted files)
* **Local repository sync** (push & pull)
* **HTTP-based object transfer** for remote syncing
* **Peer discovery over local network (UDP broadcast)**
* **Lightweight mesh server** to serve repository objects

---

## 🛠️ Tech Stack

* Python
* File system operations
* SHA-1 hashing (`hashlib`)
* Compression (`zlib`)
* HTTP requests (`requests`)
* Socket programming (UDP)
* Simple HTTP server

---

## 📦 Project Structure

```
MiniGit/
├── minigit.py
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚙️ Usage

### Initialize a repository

```
python minigit.py init
```

### Add files

```
python minigit.py add file.txt
python minigit.py add folder/
```

### Commit changes

```
python minigit.py commit -m "Initial commit"
```

### Check status

```
python minigit.py status
```

### View commit history

```
python minigit.py log
```

### Branch operations

```
python minigit.py branch new-branch
python minigit.py checkout new-branch
python minigit.py checkout -b feature-branch
```

---

## 🔄 Syncing Repositories

### Clone a repository

```
python minigit.py clone <source_path> <destination_path>
```

### Push changes

```
python minigit.py push <destination_path>
```

### Pull changes

```
python minigit.py pull <source_path>
```

---

## 🌐 Network Features

### Start mesh server

```
python minigit.py meshserver --port 8080
```

### Discover peers

```
python minigit.py peers
```

### Listen for peers

```
python minigit.py peers --listen
```

---

## 💡 What I Learned

* How Git stores data internally using objects and hashes
* How commits form a linked history structure
* How branching works under the hood
* Basics of distributed systems and synchronization
* Networking concepts like HTTP transfer and UDP broadcasting

---

## ⚠️ Limitations

* No merge conflict resolution
* No rebase functionality
* No remote tracking branches (like origin/master)
* Designed for learning purposes, not production use

---

## 📌 Note

This project was built to deepen understanding of version control systems and system design concepts.
It is not intended to replace Git, but to explore how similar systems can be implemented from scratch.
