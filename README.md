# uWS websocket for node
-------------------

## Why

- port of UWS from C++ for [DEPRECATED](https://www.reddit.com/r/node/comments/91kgte/uws_has_been_deprecated/) npm build

### Use

```
  npm install --save https://github.com/usertoken/uws.git
```

```
  const http = require('http');
  const express = require('express');
  const socketIO = require('socket.io');
  const uws = require('uws');

  const app = express();
  const server = http.Server(app);
  const io = socketIO(server);

  io.ws = new uws.Server({ perMessageDeflate: false, noServer: true });

  io.on('connection', (socket) => {
    io.emit('data', 'hello!'); 
    // or
    socket.emit('data', 'hello')
  });


  server.listen(3000, () => console.log('Socket.IO Running...'));
```
- Original C++ [SOURCE](https://github.com/uNetworking/uWebSockets)

