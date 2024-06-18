## Page Not Found

- This type of error occurs into your project when a user searchs for page that has not been registered into the router path of the project.Example when a user is into the project and finds a program hving this path `\results` but your project doesn't have that path.

- To solve this problem it depends but the first thing you have to think if that path is needed into your project or not if is not needed then you need to add the not found page but if it's needed you have to add corect path for the project.Example of Not found page and route.

```jsx
import {
  Route,
  RouterProvider,
  createBrowserRouter,
  createRoutesFromElements,
} from "react-router-dom";

// layout
import RootLayout from "./layout/RootLayout";
import EventLayout from "./layout/EventsLayout";

// pages
import NotFound from "./pages/NotFound";
import Home, { eventLoader } from "./home/Home";
import EventDetails, { eventLoaderDetails } from "./events/EventDetails";
import Event from "./events/Events";
import Create from "./auth/Create";
import Dashboard from "./pages/Dashboard";
import Profile from "./user/Profile";
import EventsError from "./events/EventsError";

const router = createBrowserRouter(
  createRoutesFromElements(
    <Route path="/" element={<RootLayout />}>
      <Route
        index
        loader={eventLoader}
        errorElement={<EventsError />}
        element={<Home />}
      ></Route>
      <Route path="events" element={<EventLayout />}>
        <Route index loader={eventLoader} element={<Event />}></Route>
        <Route
          path=":id"
          loader={eventLoaderDetails}
          errorElement={<EventsError />}
          element={<EventDetails />}
        ></Route>
      </Route>
      <Route path="create" element={<Create />}></Route>
      <Route
        path="dashboard"
        loader={eventLoader}
        element={<Dashboard />}
      ></Route>
      <Route path="profile" element={<Profile />}></Route>
      <Route path="*" element={<NotFound />}></Route>
    </Route>
  )
);
export default function App() {
  return (
    <div>
      <RouterProvider router={router}></RouterProvider>
    </div>
  );
}
```

- Example of not found page.

```jsx
import { NavLink } from "react-router-dom";

export default function NotFound() {
  return (
    <div className="p-8">
      <h1 className="font-bold">NotFound</h1>
      <p>
        Page Not Found return to{" "}
        <NavLink to="/" className="font-bold hover:underline text-blue">
          Homepage
        </NavLink>
      </p>
    </div>
  );
}
```

## JSON parse tools limit

- Sometimes a person can be searching a file in json format which is locally but also a file which is from API endpoints.Let's say example you have event page where you display the list of events but there is a link to events details and events are linked by an id such that from 1 and so on, so what happens here is that when a uyser tries to request event which is out of range using this path `http://localhost:5173/events/122` the event in which a user finds doesn't exits so what happens a user gets this error.

```json
Unhandled Thrown Error!
JSON.parse: unexpected character at line 1 column 1 of the JSON data
💿 Hey developer 👋

You can provide a way better UX than this when your app throws errors by providing your own errorElement props on <Route>.
```

- The server is trying to fetch for a data for an event which does not exist so what is needed is here is adding a way to throw this error when a response is not ok when fetching data.

```jsx
export const eventLoader = async () => {
  const response = await fetch("http://localhost:3003/events");

  //   handling response
  if (!response.ok) {
    throw Error("Could not fetch event");
  }
  return response.json();
};
```

- After adding that what follows is creating a page to throw an error

```sh
# create event file
touch eventError.jsx
```

```jsx
import { NavLink, useRouteError } from "react-router-dom";

export default function EventsError() {
// use route error for handling json limit error    
  const error = useRouteError();
  return (
    <div className="p-8">
      <h1 className="font-bold">Error</h1>
      <p>{error.message}</p>
      <p>The Event You are Lokking For Was Not Found</p>
      <NavLink to="/" className="text-blue-700 underline font-semibold">
        Back to Homepage
      </NavLink>
    </div>
  );
}
```

- add a prop errorElement into the route in which an error has occured.

```jsx
<Route
  path=":id"
  loader={eventLoaderDetails}
  errorElement={<EventsError />}
  element={<EventDetails />}
></Route>
```
