







REACT ROUTER
Assignments



React Router is a popular routing library for building single-page applications (SPAs) using React. It provides a way to handle navigation and URL routing in a React application. With React Router, you can define different routes in your application and map them to different components, enabling you to create a multi-page experience within a single page.

React Router helps in managing the application's UI state as the URL changes. It allows you to create nested routes, handle dynamic routing parameters, and perform programmatic navigation within your React application. React Router works well with both React and React Native, making it a versatile tool for building web and mobile applications.

Here are some key concepts and components in React Router:

1. BrowserRouter: It provides the routing functionality using the HTML5 history API. It's typically used as the top-level component in your application.

2. Switch: It renders the first matching route within its component hierarchy. It's useful when you want to render only one route at a time.

3. Route: It renders a component when the URL matches a specified path. You can define multiple routes in your application, each mapped to a different component.

4. Link: It is used to create links within your application. It generates an anchor tag with the appropriate URL based on the specified route.

5. useParams: It is a hook provided by React Router that allows you to access the dynamic parameters in the URL.

These are just a few of the components and concepts provided by React Router. The library offers additional features, such as route guarding, redirecting, and nested routing, to help you build robust navigation systems in your React applications.

To use React Router in your project, you need to install it as a dependency. You can do this by running the following command in your project's root directory:

```shell
npm install react-router-dom
```

Once installed, you can import the necessary components from `react-router-dom` and start defining routes and implementing navigation in your React application.

Here's a simple example that demonstrates how to use React Router:

```jsx
import React from 'react';
import { BrowserRouter, Switch, Route, Link } from 'react-router-dom';

const Home = () => <h1>Home</h1>;
const About = () => <h1>About</h1>;
const Contact = () => <h1>Contact</h1>;

const App = () => {
  return (
    <BrowserRouter>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/about">About</Link>
          </li>
          <li>
            <Link to="/contact">Contact</Link>
          </li>
        </ul>
      </nav>

      <Switch>
        <Route exact path="/">
          <Home />
        </Route>
        <Route path="/about">
          <About />
        </Route>
        <Route path="/contact">
          <Contact />
        </Route>
      </Switch>
    </BrowserRouter>
  );
};

export default App;
```

In this example, the `BrowserRouter` component wraps the navigation and route components. The `Link` components are used to navigate between different routes. The `Switch` component renders the first matching route within its hierarchy.

When the URL matches a particular path, the corresponding component defined in the `Route` component is rendered. For example, when the URL is "/about," the `About` component will be displayed.

React Router provides a flexible and powerful way to handle routing and navigation in your React applications, making it easier to build complex user interfaces with multiple views and pages.