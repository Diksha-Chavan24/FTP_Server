# FTP_Server

## Overview

**FTP_Server** is a client-server application built using **TCP socket programming in C**.

It allows a client to request a file from the server, and the server sends the file along with its size. The client then downloads and stores it locally.

> Note: This is a custom file transfer system, not a full FTP protocol implementation.

---

## Project Files

```id="eqp09z"
program686.c  → Server Application
program687.c  → Client Application
Makefile      → Compilation helper
README.md     → Documentation
```

---

## Features

* TCP-based communication
* Multi-client support using `fork()`
* Header-based protocol (`OK <size>` / `ERR`)
* Supports text and binary files
* Efficient chunk-based file transfer

---

## Technologies Used

* C Programming
* Linux System Calls
* Socket Programming (TCP/IP)

---

## Working

### Step 1: Client sends file name

```id="y1lmnf"
Demo.txt
```

### Step 2: Server responds

* If file exists:

```id="mghyqo"
OK <file_size>
```

* If not:

```id="sqwx36"
ERR
```

### Step 3: File Transfer

* Server sends file data
* Client saves it into a new file

---

## Compilation

```bash id="9s1q4y"
gcc program686.c -o server
gcc program687.c -o client
```

---

## Execution

### Start Server

```bash id="7g7s6n"
./server 9000
```

### Run Client

```bash id="bgzq2r"
./client 127.0.0.1 9000 Demo.txt Output.txt
```

---

## Example

```id="vd71d8"
Client: Request → Demo.txt
Server: OK 2048
Client: Download complete...
```

---

## Future Improvements

* Multi-threading using pthread
* File upload support
* Encryption for secure transfer
* Progress indicator

---


---

## 🔹 License

Educational project
