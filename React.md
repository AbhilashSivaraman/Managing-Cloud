### Understanding React

React is a popular JavaScript library for building user interfaces, especially single-page applications. It allows developers to create reusable UI components and manage the state of the application effectively. Here are the key concepts you'll need:

1. **Components**: Reusable pieces of UI that can be nested, managed, and handled independently. Components can be either class-based or function-based (functional components).
2. **JSX**: A syntax extension that allows you to write HTML elements within JavaScript.
3. **State**: An object that holds some information that may change over the lifetime of the component.
4. **Props**: Short for properties, props are read-only attributes used to pass data from one component to another.
5. **Routing**: Managing navigation within a single-page application, allowing different components to be displayed based on the URL.

### Setting Up Your React Environment

1. **Install Node.js and npm**: React requires Node.js and npm (Node Package Manager).
2. **Create a React App**: Use the command `npx create-react-app my-app` to set up a new React project.

### Components

#### Creating a Functional Component

```jsx
// src/components/Hello.js
import React from 'react';

function Hello() {
  return <h1>Hello, World!</h1>;
}

export default Hello;
```

#### Using the Component

```jsx
// src/App.js
import React from 'react';
import Hello from './components/Hello';

function App() {
  return (
    <div>
      <Hello />
    </div>
  );
}

export default App;
```

### Routes

For routing, we'll use `react-router-dom`. Install it using npm:

```bash
npm install react-router-dom
```

#### Setting Up Routes

```jsx
// src/App.js
import React from 'react';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Login from './components/Login';
import Signup from './components/Signup';
import Home from './components/Home';

function App() {
  return (
    <Router>
      <div>
        <Switch>
          <Route exact path="/" component={Home} />
          <Route path="/login" component={Login} />
          <Route path="/signup" component={Signup} />
        </Switch>
      </div>
    </Router>
  );
}

export default App;
```

### Login and Signup Components

#### Login Component

```jsx
// src/components/Login.js
import React, { useState } from 'react';
import { Link } from 'react-router-dom';

function Login() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSubmit = (event) => {
    event.preventDefault();
    // Handle login logic here
    console.log('Email:', email, 'Password:', password);
  };

  return (
    <div>
      <h2>Login</h2>
      <form onSubmit={handleSubmit}>
        <div>
          <label>Email:</label>
          <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} />
        </div>
        <div>
          <label>Password:</label>
          <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} />
        </div>
        <button type="submit">Login</button>
      </form>
      <p>Don't have an account? <Link to="/signup">Signup</Link></p>
    </div>
  );
}

export default Login;
```

#### Signup Component

```jsx
// src/components/Signup.js
import React, { useState } from 'react';
import { Link } from 'react-router-dom';

function Signup() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSubmit = (event) => {
    event.preventDefault();
    // Handle signup logic here
    console.log('Email:', email, 'Password:', password);
  };

  return (
    <div>
      <h2>Signup</h2>
      <form onSubmit={handleSubmit}>
        <div>
          <label>Email:</label>
          <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} />
        </div>
        <div>
          <label>Password:</label>
          <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} />
        </div>
        <button type="submit">Signup</button>
      </form>
      <p>Already have an account? <Link to="/login">Login</Link></p>
    </div>
  );
}

export default Signup;
```

### Home Component

```jsx
// src/components/Home.js
import React from 'react';

function Home() {
  return <h2>Welcome to the Home Page</h2>;
}

export default Home;
```

### Running Your App

After setting everything up, run your React app using:

```bash
npm start
```

This will start a development server and open your app in the browser. Now you can navigate to `/login` and `/signup` to see your components in action.