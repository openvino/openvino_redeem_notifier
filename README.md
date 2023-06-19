# Redeem Notifications Server

This is a simple Express server with WebSocket functionality. It listens on port 8081 and allows WebSocket connections to be established. It also includes a route to handle a POST request for sending messages to connected WebSocket clients.

## Prerequisites

- [Node.js](https://nodejs.org) installed on your machine.

## Installation

1. Clone the repository or download the source code.
2. Open a terminal and navigate to the project directory.
3. Run the following command to install the required dependencies:

   ```shell
   npm install
   ```

## Usage

1. Open a terminal and navigate to the project directory.
2. Start the Express server by running the following command:

   ```shell
   npm start
   ```

3. The server will start listening on port 8081.
4. To establish a WebSocket connection, use a WebSocket client library or tool and connect to `ws://localhost:8081`.
5. Once connected, you can send and receive messages through the WebSocket connection.

## API Endpoint

The server provides a single API endpoint to send messages to all connected WebSocket clients.

### Endpoint

`POST /api/sendMessage`

### Request

The request should be a JSON object with the following structure:

```json
{
  "message": "Notification updated!"
}
```

### Response

- If the message is successfully sent to all connected clients, the server will respond with a JSON object:

  ```json
  {
    "success": true
  }
  ```

- If an error occurs during message sending, the server will respond with a JSON object:

  ```json
  {
    "error": "Internal Server Error"
  }
  ```

## WebSocket Events

The server emits the following events related to WebSocket connections:

- `"connection"`: This event is emitted when a new WebSocket client connects to the server.
- `"message"`: This event is emitted when a message is received from a WebSocket client.
- `"close"`: This event is emitted when a WebSocket client disconnects from the server.

You can listen for these events and perform actions based on them.

