### Conceptual Exercise

Answer the following questions below:

- What is a JWT?
  - JSON Web Token - a way to do user authorization in web apps
  - Authenitication via Token 
  - Makes a request with username/password to AJAX login route
  - Server authenticates & returns token in JSON
    - Token is encoded & signed with open standard, "JSON web token"
  - Front-end Javascript recieves token & stores (in var or localstorage)
  - For every future request, browser sends token in request
    - server gets token from request & validates token

- What is the signature portion of the JWT?  What does it do?
  - Header: metadata about token (signing algorithm & type of token)
  - Payload: data to be stored in token (typically an object like username, color, etc)
  - Signature: version of header & payload, signed with a secret key
    - uses algorithm specified in header

- If a JWT is intercepted, can the attacker see what's inside the payload?
  -  Yes, a JWT can be decoded by using the JWT decode() method. Important not to use JWT to transmit any sensitive info

- How can you implement authentication with a JWT?  Describe how it works at a high level.
  - JWT authentication works by signing a token for a user that often has a few relevant details about the user(like username and admin status) in the payload. THe token is signed with a secret key known only to the server and transmitted upon an initial registration or login. Then, with every subsequent request to the application, the JWT is required to send the request body, header, query string, etc in order to access a particular source. The JWT is then verified, confirming the signature actually works with the server's secret key, then the user can proceed. Often, user information from the JWT payload may be stored in the session for the life of that request (or possibly longer) in order to determine that you are actually the current user and give you authorization to various resources accordingly.

- Compare and contrast unit, integration and end-to-end tests.
  - A unit test is a test of a particular function and how well it works on it's own. 
  - Integration tests test the interconnectivity of multiple functions, often testing a particular app feature and all it's component parts at once
  - End-to-end test are more comprehensive and will test the entire application in order to evaluate the entire user experience across the app.

- What is a mock? What are some things you would mock?
  - a mock is basically a way of faking a certain function's output in order to skip the actual running of that function. This can be useful when the function has already been thoroughly tested elsewhere and running it again in another unit test would be redundant or even slow down the test. Things that are often mocked are time intensive AJAX requests, reading and writing to files, or functions with random results (like Math.random).

- What is continuous integration?
  - A software development practice where members of a team integrate their work frequently, leading to multiple integrations per day. The practice can be very useful in creating a more robust application since no functionality will be built without unit and integration tests to make sure it works with the existing build.

- What is an environment variable and what are they used for?
  - An environment variable is a variable that is accessible by multiple applications in that environment. Just like a global variable in a file is accessible by that entire file, environment variables can be accessed across the entire environment which is why in an application we can bring in environment variables into any file. Typically we use them when we need to keep things secret since environment variables won't be seen directly if .env is in .gitignore. We can also use them if we need to access something everywhere.

- What is TDD? What are some benefits and drawbacks?
  - TDD (Test Driven Development) is a practice in development in which the programmer will start by writing tests, then begin building out the application to satisfy those tests. This can be useful in assuring you know exactly what you want a program to do or not do and can keep you from making mistakes that may "break" other parts of an application. It tends to be a bit slower and can get a little excessive when there are more lines of test code than actual production code.



- What is the value of using JSONSchema for validation?

- What are some ways to decide which code to test?
  - The easiest code to start with is the code that will be hit when everything goes as expected. This "happy" path can usually be tested pretty simply to see that there was a "successful" response from the server or output of a function. Then, it's important to think of edge cases and test code that may be run when a user attempts to do things "incorrectly". if there is really complex code that is likely to break, it should be tested more throughly, same for code that is more important or is used more frequently.

- What does `RETURNING` do in SQL? When would you use it?
  - RETURNING is a keyword used in SQL to select rows you want when inserting, updating, or deleting data into a table. It's kind of like using SELECT to get back rows of data when querying a table. Just state what columns you want returned after the word, RETURNING. You can then check to see if a value is returned by using: result.rows.length === 0.

- What are some differences between Web Sockets and HTTP?
  - HTTP is a pretty big protocol with a lot of information in the body and headers that gets passed back in forth while websockets are much smaller. Websockets, unlike HTTP are alse stateful, meaning they stay connected after a request has been made, enabling them to be much faster and allows for them to continuously display information to the user without another request having to be made. Examples of websocket uses are stock trading websites, chat applications or gaming applications.

- Did you prefer using Flask over Express? Why or why not (there is no right
  answer here --- we want to see how you think about technology)?
