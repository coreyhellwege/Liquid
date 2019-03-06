# Testing

## Basics

Testing is commonly split into three sections: 

- #### Manual testing
Manual Testing is a process of finding out the defects or bugs in a software program. In this method the tester plays the role of end user and verifies that all the features of the application are working correctly, without using any automation tools. The tester prepares a test plan document which describes the detailed and systematic checks. Test cases are planned to cover almost 100% of the software application and are therefore time consuming.

- #### Automated testing
Automated Testing involves us then writing those manual steps into reusable JS functions so that we don't need to spend so much time testing the same things over and over again.

- #### Third-party automated test runners
Test Runners such as Jest can be used to test our API. Jest is a JavaScript testing Framework which allows us to write test suites to test particular parts of our application. It helps us to understand why things break and gives really good feedback.

## Manual Testing

This is an example spreadsheet testing authentication routes of a web application:

*Note: Front-End testing was completed in-browser. Back-End testing was completed using Postman.*

| Back-End | | | | | |
| --- | --- | --- | --- | --- | --- |
| **Verb** | **Endpoint** | **Context** | **Status** | **Passed** | **Outcome**
| GET | / | Testing API connection | 200 | True | Got message from API |
| GET | /protected/resources | No token | 400 | True | Error response |
| GET | /protected/resources | With token | 200 | True | Accessed the protected resources |
| POST | /login | Incorrect Username | 403 | True | Error response |
| POST | /login | Correct Username & Password | 200 | True | Received token |

<br>

| Front-End | | | | 
| --- | --- | --- | --- |
| **URL** | **Context** | **Passed** | **Outcome**
| /protected | No token | True | Redirected to login route successfully
| /protected | With token | True | Accessed the protected resources

## Automated Testing

- It's convention to store test scripts within a folder labelled `__tests__`

*Example folder structure:*

```
project
│   README.md
│   api.js
│   package.json    
└── __tests__
│   │   authentication.js
```

### Example Test Script

We are going to write some functions to test our API by making HTTP requests using Axios

Firstly, let's write a script to test a successful connection to our app in the browser:

*authentication.js*
```javascript
const axios = require('axios');

const url = 'http://localhost:3000';

const testConnection = () => {
  axios.get(url)
    if (resp.status === 200) {
      console.log('Passed test!')
    } else {
      console.error('Failed test')
    }
    .catch(err => console.error('Failed test'));
}

testConnection();
```

To make it easier to run your test file, you can add it to the 'test' script:

*package.json*
```json
{
  "scripts": {
    "test": "node __tests__/authentication.js"
  }
}
```

Now in your terminal you only need to run:
```bash
npm test
```

We are now going to test accessing protected routes.

So, let's write a test case for accessing a protected route with no token:

*authentication.js*
```javascript
const testProtectedResourcesNoToken = () => {
  axios.get(`${url}/protected/resources`)
    .then(resp => {
      console.error('Failed test');
    })
    .catch(err => {
      if (err.resp === 400) {
        console.log('Passed test!');
      } else {
        console.error('Failed test');
      }
    });
}

testProtectedResourcesNoToken();
```

Now let's write a test case for accessing a protected route with a token:

*(Note: Our app expects a token to be passed through the headers of the request)*

*authentication.js*
```javascript
const testProtectedResourcesWithToken = () => {
  const token = 'sdg87syg4wti43bfg98v4h3f32ubcwemsafdncviw34'
  const options = {
    headers: {
      token
    }
  }
  axios.get(`${url}/protected/resources`, options)
    .then(resp => {
      if (resp.status === 200) {
      console.log('Passed test!')
      } else {
        console.error('Failed test')
      }
    })
    .catch(err => {
        console.error('Failed test');
    });
}

testProtectedResourcesWithToken();
```

## Third-Party Automated Test Runners

Jest documentation: https://jestjs.io/docs/en/getting-started.html

