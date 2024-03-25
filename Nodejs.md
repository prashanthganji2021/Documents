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
```javascript
import rateLimit from 'express-rate-limit';

export const rateLimiterUsingThirdParty = rateLimit({
  windowMs: 24 * 60 * 60 * 1000, // 24 hrs in milliseconds
  max: 100,
  message: 'You have exceeded the 100 requests in 24 hrs limit!', 
  standardHeaders: true,
  legacyHeaders: false,
});
export { rateLimiterUsingThirdParty } from './rateLimiter';
app.use(rateLimiterUsingThirdParty)
```

**How can you avoid callback hells?**
- Callback hell is a situation where multiple nested callbacks are used in a program, making the code difficult to read and maintain.
example of callback hell:
```javascript
fs.readFile('file1.txt', (err, data) => {
  if (err) {
    console.error(err);
  } else {
    fs.readFile('file2.txt', (err, data) => {
      if (err) {
        console.error(err);
      } else {
        fs.readFile('file3.txt', (err, data) => {
          if (err) {
            console.error(err);
          } else {
            console.log(data);
          }
        });
      }
    });
  }
});
```

- To avoid callback hell, you can use promises or async/await in Node Js.
example of using promises:

**When are background or worker processes useful?**
- Background or worker processes are useful when you need to perform long-running or CPU-intensive tasks in Node Js.
- like RabbitMQ, Redis, and ZeroMQ can be used to implement background or worker processes in Node Js. to handle tasks such as sending emails, processing images, or generating reports.


**Name the types of API functions in Node?**
- There are four types of API functions in Node Js:
1. Asynchronous, non-blocking functions: These functions do not block the execution of the program and return immediately.
2. Synchronous, blocking functions: These functions block the execution of the program until the operation is completed.
3. Asynchronous, blocking functions: These functions block the execution of the program but return immediately.
4. Synchronous, non-blocking functions: These functions do not block the execution of the program but return immediately.


**Explain chaining in Nodejs?**
- Chaining in Node Js is a technique used to execute multiple asynchronous operations in a sequential order.
- It allows you to chain multiple asynchronous operations together and execute them one after the other.
```javascript
const fs = require('fs');

fs.readFile('file1.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
  } else {
    console.log(data);
    fs.readFile('file2.txt', 'utf8', (err, data) => {
      if (err) {
        console.error(err);
      } else {
        console.log(data);
      }
    });
  }
});
```



### Basic Questions (1-20)
1. What is Node.js?
2. Explain the event-driven architecture of Node.js.
3. What is NPM? How do you use it?
4. Differentiate between synchronous and asynchronous code in Node.js.
5. What is a callback function in Node.js? Provide an example.
6. What are the global objects in Node.js?
7. How do you handle errors in Node.js?
8. What is the purpose of the `package.json` file in a Node.js application?
9. How can you read and write files in Node.js?
10. Explain the purpose of the `process` object in Node.js.
11. What are streams in Node.js? Give an example of stream usage.
12. What is middleware in the context of Express.js?
13. Explain the difference between `require()` and `import` in Node.js.
14. How do you debug a Node.js application?
15. What is the purpose of the `Buffer` class in Node.js?
16. What is the event loop in Node.js?
17. How do you handle HTTP requests in Node.js?
18. What is the purpose of the `os` module in Node.js?
19. Explain the concept of clustering in Node.js.
20. What is a Promise in Node.js? How do you use it?

### Intermediate Questions (21-50)
21. What is the difference between `setImmediate()` and `setTimeout()` in Node.js?
22. How do you use environment variables in a Node.js application?
23. What is the purpose of the `cluster` module in Node.js?
24. Explain the role of the `util` module in Node.js.
25. What is JWT (JSON Web Token) and how is it used in Node.js?
26. What are child processes in Node.js? When would you use them?
27. How do you implement authentication in a Node.js application?
28. Explain the concept of middleware chaining in Express.js.
29. What is the purpose of the `crypto` module in Node.js?
30. How can you handle file uploads in Node.js?
31. Explain the concept of RESTful APIs and how to create them using Node.js.
32. What is the purpose of the `net` module in Node.js?
33. How do you manage sessions in a Node.js application?
34. What are template engines in Node.js? Name a few popular ones.
35. Explain the role of the `assert` module in Node.js testing.
36. How do you handle CORS (Cross-Origin Resource Sharing) in a Node.js application?
37. What is the purpose of the `querystring` module in Node.js?
38. Explain the difference between stateful and stateless applications in the context of Node.js.
39. How do you perform unit testing in Node.js?
40. What is the purpose of the `URL` module in Node.js?

### Advanced Questions (51-80)
41. What is GraphQL and how does it compare to RESTful APIs in Node.js?
42. Explain the concept of microservices architecture and how Node.js fits into it.
43. How do you implement caching in a Node.js application?
44. What is WebSockets and how can you use them in Node.js?
45. What are worker threads in Node.js? When would you use them?
46. Explain the role of the `dgram` module in Node.js networking.
47. How do you implement rate limiting in a Node.js application?
48. What is server-side rendering (SSR) and how can you achieve it in Node.js?
49. Explain the concept of a message broker and how it's used in Node.js applications.
50. How do you handle database connections in Node.js?

### Expert Questions (81-100)
51. What are the differences between the Node.js event loop and browser event loops?
52. How does V8 optimize JavaScript code in Node.js?
53. Explain the concept of non-blocking I/O in Node.js.
54. What is the role of libuv in Node.js and how does it work?
55. How can you implement a custom CLI (Command Line Interface) tool in Node.js?
56. What is garbage collection in Node.js and how does it impact performance?
57. Explain the concept of graceful shutdown in a Node.js application.
58. What are the best practices for securing a Node.js application?
59. How do you optimize the performance of a Node.js application?
60. Explain the differences between callbacks, promises, and async/await in Node.js.
61. How do you handle memory leaks in a long-running Node.js process?
62. What is the role of the `fs` module in managing file systems in Node.js?
63. How can you implement real-time communication in a Node.js application?
64. Explain the concept of microtask queue in Node.js event loop.
65. How do you implement distributed tracing in a Node.js application?
66. What are some strategies for logging and monitoring Node.js applications?
67. How do you handle database migrations in a Node.js application?
68. Explain the concept of WebAssembly and its integration with Node.js.
69. How do you handle long-running tasks in a Node.js application without blocking the event loop?
70. What is the purpose of the `zlib` module in Node.js?

### Node.js Frameworks and Tools (71-90)
71. What is Express.js and why is it popular in Node.js development?
72. What are the advantages of using NestJS for building Node.js applications?
73. Explain the concept of middleware in Koa.js and how it differs from Express.js.
74. How does Socket.io simplify real-time communication in Node.js?
75. What is Fastify and how does it compare to Express.js in terms of performance?
76. How can you use Sequelize for ORM (Object-Relational Mapping) in a Node.js application?
77. Explain the role of Mongoose in MongoDB integration with Node.js.
78. What is PM2 and how does it help in managing Node.js applications?
79. How do you use Jest for testing Node.js applications?
80. What is Webpack and how can you use it with Node.js for bundling and optimization?

### Deployment and Scaling (91-100)
81. How do you deploy a Node.js application to a production server?
82. What are the considerations for scaling a Node.js application horizontally?
83. How can you use Docker to containerize a Node.js application?
84. Explain the role of load balancers in scaling Node.js applications.
85. What is continuous integration/continuous deployment (CI/CD) and how do you implement it for a Node.js project?
86. How do you monitor the performance of a Node.js application in production?
87. What are the best practices for securing the infrastructure hosting a Node.js application?
88. How can you use AWS Lambda with Node.js for serverless computing?
89. What is Kubernetes and how can it be used for orchestrating Node.js applications?
90. How do you implement auto-scaling for a Node.js application based on traffic patterns?


### Security and Performance (91-100)
91. What are some common security vulnerabilities in Node.js applications and how can you mitigate them?
92. Explain the concept of cross-site scripting (XSS) and how to prevent it in a Node.js application.
93. How can you secure sensitive data such as API keys and database credentials in a Node.js application?
94. What is SSL/TLS encryption and how do you implement it in a Node.js server?
95. What are some best practices for optimizing the performance of a Node.js application?
96. How do you implement caching strategies to improve the performance of a Node.js application?
97. Explain the role of CDNs (Content Delivery Networks) in improving the performance of a Node.js application.
98. What is load testing and how do you perform it on a Node.js application?
99. How can you use profiling tools to identify performance bottlenecks in a Node.js application?
100. What are some techniques for scaling a Node.js application vertically?



### more repeated questions
- What is the purpose of the `util` module in Node.js?
- What is JWT (JSON Web Token) and how is it used in Node.js?
- What are child processes in Node.js? When would you use them?
- How do you implement authentication in a Node.js application?
- Explain the concept of middleware chaining in Express.js.
- What is the purpose of the `crypto` module in Node.js?
- How can you handle file uploads in Node.js?
- Explain the concept of RESTful APIs and how to create them using Node.js.
- What is the purpose of the `net` module in Node.js?
- How do you manage sessions in a Node.js application?
- What are template engines in Node.js? Name a few popular ones.
- Explain the role of the `assert` module in Node.js testing.
- How do you handle CORS (Cross-Origin Resource Sharing) in a Node.js application?
- What is the purpose of the `querystring` module in Node.js?
- Explain the difference between stateful and stateless applications in the context of Node.js.
- How do you perform unit testing in Node.js?
- What is the purpose of the `URL` module in Node.js?
- What is GraphQL and how does it compare to RESTful APIs in Node.js?
- Explain the concept of microservices architecture and how Node.js fits into it.
- How do you implement caching in a Node.js application?
- What is WebSockets and how can you use them in Node.js?
- What are worker threads in Node.js? When would you use them?
- Explain the role of the `dgram` module in Node.js networking.
- How do you implement rate limiting in a Node.js application?
- What is server-side rendering (SSR) and how can you achieve it in Node.js?
- Explain the concept of a message broker and how it's used in Node.js applications.
- How do you handle database connections in Node.js?
- What are the differences between the Node.js event loop and browser event loops?
- How does V8 optimize JavaScript code in Node.js?
- Explain the concept of non-blocking I/O in Node.js.





