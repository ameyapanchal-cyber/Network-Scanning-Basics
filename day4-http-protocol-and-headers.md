### Objective
The objective of this writeup is to understand how communication between a user and a server occurs through a website using the HTTP protocol, and how HTTP headers control behavior, security, and access in web applications.

---

### Web Basics I Learned
- A developer needs a server to host a website so that it remains continuously available on the internet and can handle user requests.
- A domain name acts as a human-friendly address that allows users to access websites without remembering IP addresses.
- Every website is associated with an IP address, and domain names are mapped to these IP addresses using DNS for easier access.

---

### HTTP Communication Flow
- The browser initiates communication by establishing a TCP connection with the web server.
- Once the TCP connection is established, the browser sends an HTTP request to the server.
- The server processes the request and generates an HTTP response.
- The browser receives the response and renders the web page for the user.

Browser → TCP connection → HTTP Request → Server  
Server → HTTP Response → Browser renders page

- HTTP runs over the TCP protocol.
- Both HTTP requests and responses contain headers and an optional body.

---

### HTTP Request Methods
- **GET**: Used to request data from the server. Parameters are usually sent in the URL.
- **POST**: Used to send data to the server, commonly for form submissions and login requests.
- **PUT**: Used to update existing resources.
- **DELETE**: Used to remove resources.

---

### Headers

#### General Headers
- **Connection**: Controls whether the TCP connection is kept open or closed.
- **Content-Encoding**: Specifies the encoding applied to the message body (e.g., gzip, br).
- **Content-Length**: Indicates the size of the message body in bytes.
- **Content-Type**: Defines the media type of the data in the message body.
- **Transfer-Encoding**: Specifies how the message body is transferred, commonly using chunked encoding.

---

### HTTP Request Smuggling
A mismatch between the **Content-Length** and **Transfer-Encoding** headers can cause desynchronization between frontend proxies and backend servers. This may lead to HTTP request smuggling, where additional hidden requests are processed without proper validation.

---

### Request Headers
- **Accept**: Specifies the content types the client can process.
- **Accept-Encoding**: Defines the content encodings supported by the client.
- **Authorization**: Used to send authentication credentials to the server.
- **Cookie**: Stores session identifiers issued by the server.
- **Host**: Indicates the domain name of the target server.
- **If-Modified-Since**: Allows the browser to check whether a resource has changed since a specific time.
- **If-None-Match**: Uses an ETag value to validate cached resources.
- **Origin**: Identifies the domain initiating the request.
- **Referer**: Indicates the URL of the previous page from which the request originated.
- **User-Agent**: Provides information about the client software generating the request.

---

### Response Headers
- **Access-Control-Allow-Origin**: Specifies which domains are allowed to access resources using cross-origin (AJAX) requests.
- **Cache-Control**: Defines how responses should be cached by the browser.
- **ETag**: A unique identifier assigned to a resource for cache validation.
- **Expires**: Specifies the expiration time of cached content.
- **Location**: Used for redirection responses.
- **Pragma**: Passes caching directives to the browser.
- **Server**: Provides information about the server software.
- **Set-Cookie**: Sends a cookie to the client for session management.
- **WWW-Authenticate**: Indicates the authentication method required when a 401 response is returned.
- **X-Frame-Options**: Controls whether a webpage can be embedded inside an iframe to prevent clickjacking attacks.

---

### Why This Matters for Security
- Headers can be manipulated.
- Cookies can be stolen.
- Misconfigured headers can lead to attacks such as session hijacking, CSRF, clickjacking, and information leakage.

---

### Learning
Before this module, I only interacted with websites through browsers. Now I understand what actually happens behind every HTTP request and response.
