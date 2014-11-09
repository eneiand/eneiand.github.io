
#### Introduction to Real-time web applications
* Polling and Long-Polling
  * Polling
    * client sends request
    * client periodically requests updates via AJAX
  * Long Polling
    * AJAX requests have a property called timeout
    * setting the timeout to a long time, reduces the number of requests
* Forever Frame
  * iframe
  * embed document, script tags are sent from the server to update the data
* HTML5 Server-Sent Events
  * EventSource object

#### HTML5 WebSockets - The Basics
* Evolution of the Web
  * academia tackled how to transfer one document to another
  * HTTP made sense, stateless etc.
  * new headers added for features, user-agent (what browser is making this request)
  * large headers were not a problem, the body far outweighed them
  * as web apps progressed to request little pieces of data more often, headers are a bigger problem
* WebSockets vs. Other Techniques
  * using websockets means you are not using HTTP anymore, you upgrade the connection
  * a handshake occurs when upgrading
  * no header overhead
* WebSockets basics
  * instantiate a websocket object
  * OnOpen, OnMessage, OnError, OnClose events
  * OnClose takes event with wasClean, code and reason
  * methods supported are Send and Close
  * failovers, auto-connect etc. require a higher library to be used

### HTML5 WebSockets - The Demo
* Server-side Code
  * WebSocketCollection, can check a request for web socket and upgrade if required
* Client-side Code
  * send JSON to the server via the websocket
  * the server takes action, then broadcasts the update to all connections
  * when the client receives the message it updates the div with the latest information
* Data Transfer Types
  * can send blobs and byte_arrays
  * on the client check type of event.data for ArrayBuffer
* Authentication
  * give the notes lists a dictionary with a guid as an id
  * add a session to the user (in the URL here)
  * only send updates to connections that share that ID
* Security
  * WS & WSS Schemes
  * Web Socket Secure -> uses TLS (like HTTPS for HTTP)
  * DOS, XSS etc.
* Fallbacks
  * Modernizer to check
* Inspecting
  * filter chrome dev tools to websockets on the network tab
* WebRTC fundemantals course for real-time streaming  
