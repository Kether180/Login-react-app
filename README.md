
react-login-get-post-app

## Task
1. create a component `Login` which contains two inputs:
    1. username
    1. password
    and a button to login.
1. render the Login component in the App component.

1. Use useState to control the inputs of the Login component. (This means storing the values of the inputs in a state and changing them by passing a function to the onChange prop of the inputs.)
1. Add a prop called `onLogin` to the Login component.

1. The onLogin prop takes a function which is called by the Login component with a token if the login was successful.

1. Create a function called `handleLogin` in the App component and pass it to the Login component via the `onLogin` prop we created. The handleLogin function takes a token as an argument when it is called by the Login component.
1. Print the token that is returned.  token=todo


## Task 2

1. Whenever the login button is clicked, take the input data for username and password and send it to the `/login` endpoint of our api at https://demo-api-react-2020.herokuapp.com/login.  
  The api expects a body which contains username and password as a json object. The HTTP method has to be `POST`. You can use fetch or axios.  
  Example for doing a POST request with axios:
```ecmascript 6
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
``` 
1. If the login request was correct (it is for username `admin` and password `demo`), a `token` is returned in the response.data object. Return

// https://jwt.io/


## Task 3
1. Create a new component called UserProfile
1. UserProfile takes the token as a prop.
1. If the token is not empty, UserProfile makes a GET request to `/user/me`. To be allowed to access that endpoint, you must set an HTTP Authorization header with the value `Bearer <token>` with `<token>` being the Jsonwebtoken you got from Login and which should already be saved in the state of App. See below for an example for the axios request.  
```ecmascript 6
axios.get('/your-endpoint', {
    headers: {'X-YourHeader': 'Your header value'},
  })
```
1. Render the username that is returned by the GET request in the UserProfile component.
## Task 4 (Optional)
1. Add a logout button which clears the token and make sure that the UserProfile does not show the Username anymore when the user is logged out.
## Task 5 (Optional)
1. Use the React Context API to pass the token to the UserProfile component. You can have a look at `session-6/hello-react-context` for an example. 
