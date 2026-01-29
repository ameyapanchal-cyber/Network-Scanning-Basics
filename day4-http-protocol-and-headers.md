### Objective
The objective of this writeup is to understand how communication of server and user happens using 
website, HTTP protocol, and how headers controls behaviour, security, and access in web application.

### Web Basics I Learned
- A developer needs a server to host a website so that it is continuously available on the internet and can handle user requests.
- A domain name acts as a human-friendly address that allows users to access websites without remembering IP addresses.
- Every website is associated with an IP address, and domain names are mapped to these IP addresses using DNS for easier access.

### HTTP Communication Flow
- The browser initiates a connection with the web server by establishing a TCP connection.
- Once the TCP connection is established, the HTTP request is sent by the browser to the web server.
- After receiving the request from the browser, the server generates an HTTP response and sends it back.
- The browser receives the response and renders the web page for the user.

Browser → TCP connection → HTTP Request → Server  
Server → HTTP Response → Browser renders page

- HTTP runs over the TCP protocol.
- Both HTTP requests and responses contain headers and an optional body.

### HTTP Request Methods
- GET: Used to request data from the server. Parameters are usually sent in the URL.
- POST: Used to send data to the server, commonly for form submissions and login requests.
- PUT: update existing data.
- DELETE: remove resources.

### Headers

## General Headers
- Connection: Controls whether the TCP connection is kept open or closed after the request/response.
- Content-Encoding: Specifies the encoding applied to the message body (e.g., gzip, br).
- Content-Length: Indicates the size of the message body in bytes.
- Content-Type: Defines the media type of the data in the message body (e.g., text/html, application/json).
- Transfer-Encoding: Specifies how the message body is transferred, commonly using chunked encoding.

# HTTP Request Smuggling
- A mismatch between Content-Length and Transfer-Encoding headers can cause
desynchronization between frontend proxies and backend servers. This may
lead to HTTP request smuggling, where additional requests are processed
without proper validation.

## Request Headers
- Accept: Tells the server what kind of content the client is willing to accept.
- Accept-encoding: what kind of content encoding the client is willing to accept.
- Authorization: Used to send authentication credentials to the server.
- Cookie: it is known as session identity which is issued by the server.
- Host: Indicates the domain name of the target server.
- If-modified-since: Browser asks the server: “Has this file changed since this date?”,If not changed, the server sends no new data to save bandwidth.
- If-none-match: Browser sends an ETag value to check if the file is the same. If the ETag matches, the server says “nothing changed” and skips sending the file.
- Origin: Identifies the origin domain (web site) initiating the request.
- Refer: Indicates the URL of the previous page (web page) from which the request was made.
- User-agent: it provides the information about the browser and the software used by the clint which generates the request.

