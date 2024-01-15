## Instructions (by dort)
Change key in Grab fingerprint action in record mode, then exit record mode and start on 30-40 threads and use IP auth for max speed.

## Setup instructions (by vast)
- Download https://bablosoft.com/shop/BrowserAutomationStudio
- Setup ur own hsw api thing to send and receive the keys
- Proxy your local connection to whatever your host is
```js
const httpProxy = require('http-proxy');
const http = require('http');
const proxy = new httpProxy.createProxyServer({
  target: {
    host: '65.108.238.149',
    port: 1001
  }
});
proxy.on('error', function (err, req, res) {
});
const proxyServer = http.createServer(function (req, res) {
  proxy.web(req, res);
});
proxyServer.on('error', function (err, req, res) {
});
proxyServer.on('upgrade', function (req, socket, head) {
  proxy.ws(req, socket, head);
});
proxyServer.listen(1001);
```
