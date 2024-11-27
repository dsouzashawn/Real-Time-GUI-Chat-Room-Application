**# Multi-Client Chat Application**  
This is a basic **multi-client chat application** implemented in **Python** using **sockets** and **threads** for communication between a server and multiple clients. The **server** broadcasts messages sent by a client to all other connected clients. **Clients** interact with the server via a simple **graphical user interface (GUI)** built using the **Tkinter** library.

---

**# Features:**
- **Server**: Handles multiple clients concurrently using threads.
- **Client**: Simple GUI for sending and receiving messages.
- **Broadcast**: Messages from one client are broadcast to all other clients.
- **Disconnect Handling**: Server removes disconnected clients from the active list.
- **Real-Time Communication**: Clients send and receive real-time updates.

---

**# Server Code: `server.py`**  
The `server.py` file manages connections with multiple clients and broadcasts messages to all clients.

**Key Components:**
- **Socket Setup**: Uses `AF_INET` (IPv4) and `SOCK_STREAM` (TCP) to listen on IP `127.0.0.1` and port `7500`.
- **Client Thread Handling**: A new thread is created for each connected client to handle messages and disconnections.
- **Message Broadcasting**: Messages from one client are broadcast to all other clients except the sender.
- **Client Management**: Clients are stored in a set; disconnected clients are removed.

---

**# Client Code: `client.py`**  
The `client.py` file represents the client application that connects to the server, sends messages, and displays messages from other clients.

**Key Components:**
- **Socket Setup**: Connects to the server at IP `127.0.0.1` and port `7500`.
- **GUI Interface**: Built with Tkinter to send and receive messages, with a **Text** widget for received messages and an **Entry** widget for typing messages.
- **Message Sending**: Client sends messages to the server, which broadcasts to others.
- **Message Receiving**: A background thread listens for messages from the server and updates the GUI.

---

**# How It Works:**
- **Server Setup**: The server listens for client connections, spawning new threads to handle communication. Messages are broadcast to all connected clients.
- **Client Setup**: Clients connect to the server, send messages, and receive real-time updates through the GUI.

---

**# Running the Application**

1. **Run the Server**:
   - Navigate to the directory containing `server.py` and run:
     ```bash
     python server.py
     ```
   - The server will start and wait for client connections.

2. **Run the Clients**:
   - Navigate to the directory containing `client.py` and run:
     ```bash
     python client.py
     ```
   - Multiple clients can be run to simulate multiple users.

3. **Communication**:
   - Type a message in the client and click "Send." Messages will appear on all clients in real-time.

4. **Disconnecting**:
   - When a client closes the window, the server will remove them from the list of active clients.

---

**# Dependencies:**
- **Python 3.x**
- **Tkinter** (for the GUI, usually pre-installed with Python)
