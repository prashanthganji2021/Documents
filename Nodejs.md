**Node Js**
- A. Node Js is a single-threaded, non-blocking, asynchronous programming language that is used to develop server-side applications. It is an open-source, cross-platform runtime environment that is used to execute JavaScript code on the server-side. Node Js is built on Chrome's V8 JavaScript engine. 


 **What is meant by single-threaded?**
- Single-threaded means that Node Js can handle only one request at a time.
- It uses a single thread to handle all the requests. 

**How does Node Js handle multiple requests?**
- Node Js uses an event-driven, non-blocking I/O model to handle multiple requests.
- It uses an event loop to handle multiple requests.
- The event loop is a mechanism that allows Node Js to handle multiple requests without blocking the execution of the program.
- When a request is received, Node Js adds it to the event loop and continues to process other requests.
- When the request is completed, Node Js sends the response back to the client.

**what is mean by  event loop in Node Js?**
- The event loop is a mechanism that allows Node Js to handle multiple requests without blocking the execution of the program.
- It is a loop that continuously checks for new events and executes the corresponding callback functions.
- The event loop is responsible for handling I/O operations, timers, and other asynchronous operations in Node Js.
example of event loop in Node Js:
```javascript
setInterval(() => {
  console.log('Hello World');
}, 1000);
```
- In this example, the setInterval function is used to print 'Hello World' every second.
- The event loop continuously checks for new events and executes the callback function every second.

**What is meant by non-blocking I/O?**
- Non-blocking I/O means that Node Js does not wait for I/O operations to complete before moving on to the next operation.
- It allows Node Js to handle multiple requests simultaneously without blocking the execution of the program.
- Node Js uses callbacks and promises to handle asynchronous operations.


**What is meant by asynchronous programming?**
- Asynchronous programming means that Node Js can execute multiple operations simultaneously without blocking the execution of the program.
- It allows Node Js to handle I/O operations, timers, and other asynchronous operations without waiting for them to complete.
- Asynchronous programming is achieved using callbacks, promises, and async/await in Node Js.

**What is the difference between synchronous and asynchronous programming?**
- Synchronous programming means that the program executes one operation at a time in a sequential order.
- Asynchronous programming means that the program can execute multiple operations simultaneously without waiting for them to complete.
- Synchronous programming blocks the execution of the program until the operation is completed.
- Asynchronous programming allows the program to continue executing other operations while waiting for the asynchronous operation to complete.

**What are the advantages of Node Js?**
- Fast execution: Node Js is built on Chrome's V8 JavaScript engine, which compiles JavaScript code into machine code, making it faster than other programming languages.
- Non-blocking I/O: Node Js uses an event-driven, non-blocking I/O model to handle multiple requests simultaneously without blocking the execution of the program.
- Scalability: Node Js is highly scalable and can handle a large number of requests with minimal resources.
- Large ecosystem: Node Js has a large ecosystem of libraries and frameworks that can be used to build server-side applications.
- Cross-platform: Node Js is a cross-platform runtime environment that can run on Windows, macOS, and Linux.

**How to handle concurrency in Node Js?**
- Concurrency means that multiple requests are being processed simultaneously.
- Node Js uses an event-driven, non-blocking I/O model to handle concurrency.
- It uses the event loop to handle multiple requests without blocking the execution of the program.

**use of crypto module in Node Js?**
- The crypto module in Node Js is used to provide cryptographic functionality.
- It provides a set of cryptographic functions that can be used to encrypt and decrypt data, generate hashes, and create digital signatures.
- The crypto module is used to secure data and protect it from unauthorized access.

**Other then JWT what can be used for authentication in Node Js?**
- Other than JWT, session-based authentication can be used for authentication in Node Js.
- Session-based authentication uses a session ID to authenticate users.
- When a user logs in, a session ID is generated and stored in a session store.
- The session ID is sent to the client, and the client sends the session ID with each request.

**How to limit the number of requests from same IP in Node Js?**
- To limit the number of requests from the same IP in Node Js, you can use the rate-limiting middleware.
- The rate-limiting middleware can be used to limit the number of requests from the same IP address within a specified time frame.
- The rate-limiting middleware can be configured to limit the number of requests per IP address, per route, or per application.


