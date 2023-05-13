


REACT ROUTER
Assignments







React Router is a popular routing library for building single-page applications (SPAs) using React. It provides a way to handle navigation and URL routing in a React application. With React Router, you can define different routes in your application and map them to different components, enabling you to create a multi-page experience within a single page.

React Router helps in managing the application's UI state as the URL changes. It allows you to create nested routes, handle dynamic routing parameters, and perform programmatic navigation within your React application. React Router works well with both React and React Native, making it a versatile tool for building web and mobile applications.

Here are some key concepts and components in React Router:

1. BrowserRouter: It provides the routing functionality using the HTML5 history API. It's typically used as the top-level component in your application.

2. Route: It renders a component when the URL matches a specified path. You can define multiple routes in your application, each mapped to a different component.

3. Link: It is used to create links within your application. It generates an anchor tag with the appropriate URL based on the specified route.

4. useParams: It is a hook provided by React Router that allows you to access the dynamic parameters in the URL.

These are just a few of the components and concepts provided by React Router. The library offers additional features, such as route guarding, redirecting, and nested routing, to help you build robust navigation systems in your React applications.

To use React Router in your project, you need to install it as a dependency. You can do this by running the following command in your project's root directory:

```shell

npm install react-router-dom

```

Once installed, you can import the necessary components from `react-router-dom` and start defining routes and implementing navigation in your React application.

Here's a simple example that demonstrates how to use React Router:

```jsx

import React, { Suspense } from 'react';
// import './App.css';
// import 'mdb-react-ui-kit/dist/css/mdb.min.css';
// import "@fortawesome/fontawesome-free/css/all.min.css";

import { createBrowserRouter } from 'react-router-dom';
import Header from "./ComComponent/Header";
import HomePage from "./HomePage";
import Feature from "./Feature";
import ConatctPage from "./ContactPage";
import AboutPage from "./AboutPage";
import Examples from "./Examples";
import BtnGroup from './ComComponent/BtnGroup';
import BtnLeft from './ComComponent/BtnLeft';
import BtnMid from './ComComponent/BtnMid';
import BtnRight from './ComComponent/BtnRight';
import ClassCompoMenu from './Components/ClassComponent/ClassCompoMenu';
import ClassCompoIntro from './Components/ClassComponent/ClassCompoIntro';
import ClassCompoJSX from './Components/ClassComponent/ClassCompoJSX';
// import ClassCompoRoute from './Components/ClassComponent/ClassCompoRoute';
// import FunctionalCompoRoute  from './Components/FunctionalComponent/FunctionalCompoRoute';

// const ClassCompoRoute = React.lazy(() => import('./Components/ClassComponent/ClassCompoRoute'));
// const FunctionalCompoRoute  = React.lazy(() => import('./Components/FunctionalComponent/FunctionalCompoRoute'));

const app = createBrowserRouter([
  {
    path:"/",
    element:<Header/>,
    children:[
      {
        // path:"/home",
        index : true ,
        element:<HomePage/>,
      },
      {
        path:"/about",
        element:<AboutPage/>,
        children:[
        {
          path:"btngroup",
          element:<BtnGroup/>,   
        },
        {
          path:"/about/btnleft",
          element:<BtnLeft/>,
        },
        {
          path:"/about/btnmid",
          element:<BtnMid/>,
        },       
        {
          path:"/about/btnright",
          element:<BtnRight/>,
          children:[
            {
              path:"/about/btnright/btnleft",
              element:<BtnLeft/>,
            },
            {
              path:"/about/btnright/btnmid",
              element:<BtnMid/>,
            },
            {
              path:"/about/btnright/btnright",
              element:<BtnRight/>,
            },
          ]
        },
     ]
   },
      {
        path:"/contact",
        element:<ConatctPage/>,
      },
      {
        path:"/feature",
        element:<Feature/>,
      },
      {
        path:"/examples",
        element:<Examples/>,
        children:[
          {
            path:"classcomponent/*",
            element:<ClassCompoMenu/>,
            children:[
              {
                path:"classcompointro",
                element:<ClassCompoIntro/>,
              },
              {
                path:"classcompojsx",
                element:<ClassCompoJSX/>,
              },
            ] 
          },
          {
            path: "functionalcomponent/*",
            element:<functionalCompoMenu/>,
            children:[
              {
                path:"functionalcompointro",
                element:<functionalCompoIntro/>, 
              },
            ]
          },
        ],
      },
    ],
  },
]);

export default app;


import React, { Component } from 'react';
import { Link, Outlet } from 'react-router-dom';

export default class ClassCompoMenu extends Component {
  render() {
    return (
       <>
          <ul>
            <li><Link to="classcompointro">Class Compo Intro</Link></li>
            <li><Link to="jsxinclasscompo">JSX in Class Compo</Link></li>
          </ul>
          <Outlet/>
       </>
    )
  }
}

```


```JSX

import React, { Component } from 'react';
import { Route, Routes } from 'react-router-dom';
import ClassCompoMenu from './ClassCompoMenu';
import WelcomeToClassCompo from './WelcomeToClassCompo.jsx';
import ClassCompojsx from './ClassCompojsx.jsx';


class ClassCompoRoute extends Component {
    render() {
        return (
            <>
                <Routes>
                    <Route path="/" element={<ClassCompoMenu />} >
                        <Route path="classcompointro" element={<WelcomeToClassCompo />} />
                        <Route path="classcompojsx" element={<ClassCompojsx />} />
                    </Route>
                </Routes>
            </>
        );
    }
}


import React, { Component } from 'react';
import { Link,Outlet } from 'react-router-dom';

class ClassCompoIntro extends Component {
  render() {
    return (
      <>
        <ul>
          <li><Link to="classcompointro">Class Compo Intro</Link></li>
          <li><Link to="classcompojsx">JSX In Class Compo</Link></li>
        </ul>
        <Outlet></Outlet>
      </>
    );
  }
}

export default ClassCompoIntro;

```

export default ClassCompoRoute;

In this example, the `BrowserRouter` component wraps the navigation and route components. The `Link` components are used to navigate between different routes. 

When the URL matches a particular path, the corresponding component defined in the `Route` component is rendered. For example, when the URL is "/about," the `About` component will be displayed.

React Router provides a flexible and powerful way to handle routing and navigation in your React applications, making it easier to build complex user interfaces with multiple views and pages.