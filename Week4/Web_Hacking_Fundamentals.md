# HTTP (HyperText Transfer Protocol) and HTTPS (HyperText Transfer Protocol Secure) 

They are both protocols used for data communication on the web.

- **HTTP**: Created by Tim Berners-Lee and his team between 1989 and 1991, HTTP defines how web browsers and servers communicate. It’s the protocol used whenever you access a website, and it transmits data like HTML, images, and videos between your browser and the server. However, HTTP itself does not include encryption, so data sent over HTTP can be intercepted and read by others.

- **HTTPS**: HTTPS is the secure version of HTTP, adding a layer of encryption using SSL/TLS (Secure Sockets Layer / Transport Layer Security). With HTTPS, data is encrypted to protect it from interception, ensuring both data privacy and integrity. Additionally, HTTPS provides authentication, meaning you can be confident you’re connected to the legitimate server and not to an impersonator, which helps prevent attacks like man-in-the-middle attacks. 

## Request and Response
A **URL** (Uniform Resource Locator) is essentially an address that specifies how and where to access a resource on the internet. When you enter a URL, your browser uses it to make requests to a web server for assets like HTML, images, and other files, downloading the responses to display the webpage.

### Parts of a URL

Here's a breakdown of each part of a URL, using an example:

- **Scheme**: Indicates the protocol to be used to access the resource, such as HTTP, HTTPS, or FTP. In the URL `http://`, the scheme is `http`.

- **User**: Some services require authentication, and a username (and password) can be included in the URL for login. For example, `user:password@`.

- **Host**: The domain name or IP address of the server you want to access, such as `tryhackme.com`.

- **Port**: Specifies the port to connect to on the server. HTTP typically uses port 80, while HTTPS uses port 443. For example, `:80` is included for HTTP in this example URL.

- **Path**: Refers to the specific resource or file location you’re trying to access on the server. In this example, `/view-room` is the path.

- **Query String**: Extra information sent to the requested path, often for identifying resources or passing data to the server. For example, `?id=1` specifies an ID in this query string.

- **Fragment**: A reference to a location within the page content, like `#task3`, allowing users to jump directly to a specific section of a page.

**Example**: In the URL `http://user:password@tryhackme.com:80/view-room?id=1#task3`, each part is defined as above, with the host `tryhackme.com`, the path `/view-room`, and a fragment `#task3` referencing a specific part of the page.

### Making a Request

To request a resource, the browser could send a simple line like:
```
GET / HTTP/1.1
```

This line alone is enough for a basic request. But to enrich the experience and provide more context, additional data called **headers** is sent along with the request. Headers contain extra information, such as the browser type, language preferences, or authentication details, which will be covered in more detail in the next section.

## HTTP Methods
HTTP methods let a client indicate the desired action when making an HTTP request. They define what the client wants to do with a resource, which can include retrieving, submitting, updating, or deleting data. Here are the most common HTTP methods:

1. **GET Request**:
   - Used to request and retrieve information from a web server without making any changes to the resource.
   - GET requests are typically used to load web pages or retrieve data.

2. **POST Request**:
   - Used for submitting data to a web server, often to create new resources or send form data.
   - This method is common in situations where data needs to be processed by the server, like submitting a form or creating an account.

3. **PUT Request**:
   - Used to update existing information on the web server.
   - If a record already exists, PUT replaces it with the new data. If it doesn’t exist, some implementations might create a new record.

4. **DELETE Request**:
   - Used to remove information or records from a server.
   - Common in applications where users can delete their data, like removing items from a cart or deleting an account.

## HTTP Status Codes

HTTP status codes are three-digit numbers returned by a server in response to a client request. They inform the client about the status of the request and can provide guidance on handling it. Here’s a breakdown of the status code ranges and common codes:

### Status Code Ranges
1. **100-199 - Informational Responses**: 
   - Indicate the initial part of the request was received, and the client can continue sending additional data.
   - These codes are less commonly used today.

2. **200-299 - Success**:
   - Signal that the client’s request was successfully processed by the server.
   
3. **300-399 - Redirection**:
   - Inform the client to look at another resource for the requested content, either temporarily or permanently.

4. **400-499 - Client Errors**:
   - Indicate that the client made an error in the request, such as missing information or unauthorized access.

5. **500-599 - Server Errors**:
   - Indicate that the server encountered an error while trying to process the request, typically due to a server issue.

### Common HTTP Status Codes
- **200 - OK**: The request completed successfully.
- **201 - Created**: A new resource was successfully created, such as after a POST request.
- **301 - Moved Permanently**: The resource has permanently moved to a new URL.
- **302 - Found**: Temporary redirection to another URL.
- **400 - Bad Request**: The server detected an error in the client’s request, such as missing or incorrect data.
- **401 - Unauthorized**: The resource requires authentication, typically needing a login.
- **403 - Forbidden**: Access to the resource is denied, even if the user is logged in.
- **404 - Not Found**: The requested page or resource does not exist.
- **405 - Method Not Allowed**: The server does not allow the requested method for the resource (e.g., a GET request where a POST is expected).
- **500 - Internal Server Error**: A generic error on the server that prevents processing the request.
- **503 - Service Unavailable**: The server is temporarily unable to handle the request, possibly due to overload or maintenance.

