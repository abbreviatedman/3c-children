

### Assignment: Parent-Child Component Architecture

**Objective:**

Create a React app that fetches data from the Star Wars API (SWAPI) and displays it using parent-child component architecture. The app will include a navbar/sidebar and presentational parent components.

### Step 1: Set Up the React Project

- Open the terminal to the `assignment` directory--the simplest way to do so is to right-click on the `assignment` folder in VS Code and select "Open in Integrated Terminal".

- In the terminal, type `npm create vite .` and hit enter/return. The `.` is important--this will create a new Vite project in the current directory.

- It will warn you that there are files here currently. Use the arrow keys and Enter/Return to select "Ignore files and continue". This allows us to keep our readme and any data/assets files we have in our new project folder.

- Choose React and then JavaScript from the following menus, using arrow keys and Enter/Return.

- Install dependencies by entering `npm install` in the terminal.

- Run the app by typing `npm run dev` in the terminal. This will provide a clickable link to open the app in your default browser, or you can navigate to the localhost URL in your browser.

### Step 2: Explore the Star Wars API (SWAPI)

Spend some time exploring the Star Wars API. Familiarize yourself with how to make requests and the structure of the data returned.

#### Access the API:

1. Visit the SWAPI documentation: [https://swapi.dev/documentation](https://swapi.dev/documentation)
2. Use your browser or a tool like Postman to make a GET request to `https://swapi.dev/api/people/1/`.
3. JSON response to understand the structure of the data.

#### Example JSON Response:

Example JSON response for a GET request to `https://swapi.dev/api/people/1/`:

```json
{
  "name": "Luke Skywalker",
  "height": "172",
  "mass": "77",
  "hair_color": "blond",
  "skin_color": "fair",
  "eye_color": "blue",
  "birth_year": "19BBY",
  "gender": "male",
  "homeworld": "https://swapi.dev/api/planets/1/",
  "films": [
    "https://swapi.dev/api/films/1/",
    "https://swapi.dev/api/films/2/",
    "https://swapi.dev/api/films/3/",
    "https://swapi.dev/api/films/6/"
  ]
  // Additional fields have been truncated for brevity
}
```

**Check**: Make sure you can successfully fetch and view this data using a tool like Postman or your browser.

Once you have reviewed and understood the structure of the JSON response, you are ready to move on to the next step.

### Step 3: Design the Navbar Component

Create a Navbar component that will serve as the top navigation bar for your app.

1. Create a file named `Navbar.jsx` in the `src` directory.
2. Inside `Navbar.jsx`, create a function that returns a `div` element with the class `navbar`.
3. Inside the `div` element, add an `h1` element with the title "Star Wars Data App".
4. Below the `h1` element, create a `div` with the class name `links` to hold the navigation links.
5. Use `props.children` inside the `links` div to render any child elements passed to the `Navbar` component.
6. Export the `Navbar` function.

Create a CSS file named `Navbar.css` in the `src` directory and add the following CSS:

**File:** `src/Navbar.css`

```css
.navbar {
  background-color: #333;
  color: white;
  padding: 10px 20px;
  text-align: center;
}

.navbar .links {
  margin-top: 10px;
}

.navbar .links a {
  color: white;
  margin: 0 10px;
  text-decoration: none;
}

.navbar .links a:hover {
  text-decoration: underline;
}
```

### Step 4: Use the Navbar Component

1. In `main.jsx`, remove the CSS import.
2. In `App.jsx`, remove everything from the return statement of the `App` function.
3. Remove all imports above the `App` function.
4. Add a `div` element to the return statement.
5. Import the `Navbar` component in your `App` component.
6. Add the `Navbar` component as a child of the `div` element.
7. **In the App component's return**, place navigation links as children to the `Navbar` component, using `a` elements with `href` attributes set to `#home`, `#about`, and `#contact`.
8. Add some placeholder content below the `Navbar` to ensure it's rendering correctly. It should show your placeholder content below the navbar with the title "Star Wars Data App" and the links.

**Check:** Verify that the `Navbar` with links is displayed at the top of your app, and the links are styled correctly. Then remove the placeholder content.

Once you've added the `Navbar` component with its links to your `App.jsx`, confirmed it renders correctly, and removed the placeholder content, you’re ready to move on to the next step.

### Step 5: Design the Sidebar Component

Create a Sidebar component that will serve as the side navigation bar for your app.

1. Create a file named `Sidebar.jsx` in the `src` directory.
2. Inside `Sidebar.jsx`, create a function that returns a `div` element with the class name `sidebar`.
3. Inside the `div` element, add an `h2` element with the text "Sidebar".
4. Below the `h2` element, create a `div` with the class name `links` to hold the navigation links.
5. Use `props.children` inside the `links` div to render any child elements passed to the `Sidebar` component.
6. Export the `Sidebar` function.

Create a CSS file named `Sidebar.css` in the `src` directory and add the following CSS:

**File:** `src/Sidebar.css`

```css
.sidebar {
  width: 250px;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background-color: #333;
  padding-top: 20px;
  color: white;
}

.sidebar .links {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: start;
  padding-left: 20px;
}

.sidebar .links a {
  color: white;
  margin: 5px 0;
  text-decoration: none;
}

.sidebar .links a:hover {
  text-decoration: underline;
}
```

### Step 6: Use the Sidebar Component

1. Import the `Sidebar` component in your `App` component.
2. Add the `Sidebar` component below the `Navbar` component in your `App` component's return statement.
3. **In the App component's return**, place navigation links as children to the `Sidebar` component, using `a` elements with `href` attributes set to `#people`, `#planets`, and `#starships`.

**Check:** Verify that the `Sidebar` with links is displayed correctly alongside the `Navbar`, and the links are styled correctly.

Once you've added the `Sidebar` component with its links to your `App.jsx` and confirmed it renders correctly, you’re ready to move on to the next step.

### Step 7: Design the Presentational Parent Component

Create a parent component that will render child components with the style and layout they need.

1. Create a file named `ParentComponent.jsx` in the `src` directory.
2. Inside `ParentComponent.jsx`, create a function and name it `ParentComponent`.
3. Add a `return` statement for the `ParentComponent` function that returns a `div` element with the class name `parent-container`.
4. Inside the `div` element, add an `h2` element with the text "Data from Star Wars API".
5. Below the `h2` element, add a `div` with the class name `data-container` to hold the child component.
6. Use `props.children` inside the `data-container` div to render any child elements passed to the `ParentComponent` component.

Create a CSS file named `ParentComponent.css` in the `src` directory and add the following CSS:

**File:** `src/ParentComponent.css`

```css
.parent-container {
  padding: 20px;
  margin: 20px 20px 20px 270px;
  background: #f0f0f0;
  border: 2px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.data-container {
  margin-top: 20px;
  padding: 20px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
  transition: box-shadow 0.3s;
}

.data-container:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}
```

**Check**: Ensure the `ParentComponent` provides its look and style by importing and using it in your App component with some test content as children. Verify that the `ParentComponent` is displayed correctly with the new styling.

### Step 8: Use the Parent Component

1. Import the `ParentComponent` component in your `App` component.
2. Add the `ParentComponent` component below the `Sidebar` component in your `App` component's return statement.
3. **In the App component's return**, place a `div` element as a child of `ParentComponent`.
4. Inside the `div` element, add an `h3` element with the text "Star Wars Characters".

**Check**: Verify that the `ParentComponent` is displayed correctly below the `Sidebar` and `Navbar` components and that the title "Star Wars Characters" is displayed with the correct styling-- an easy one to check is if the background color is correct.

Once you've added the `ParentComponent` with its title to your `App.jsx` and confirmed it renders correctly, you’re ready to move on to the next step.

### Step 9: Create the Child Component

Create a child component that will display the data fetched from the Star Wars API.

1. Create a file named `ChildComponent.jsx` in the `src` directory.
2. Inside `ChildComponent.jsx`, create a function expression and name it `ChildComponent`.
3. Initialize a state variable called `data` with an empty array using the `useState` hook.
4. Import the `useEffect` hook and create a `useEffect` call.
5. Inside the `useEffect` call, create an `async` function named `fetchData`.
6. In the `fetchData` function, make a `fetch` call to the URL `https://swapi.dev/api/people` and store the result in a variable.
7. Convert the result to JSON and store it in another variable.
8. Update the `data` state variable with the JSON result.
9. Call the `fetchData` function inside the `useEffect`.
10. Inside the `ChildComponent` function, add a `return` statement that returns a `div`.
11. Inside the `div` element, map over the `data` state variable and return a nested `div` element for each item in the `data` array. Give each nested `div` the class of `data-item`.
12. For each item, display the `name`, `height`, `mass`, and `hair_color` properties inside `h3` and `p` elements.
13. Export the `ChildComponent` function.

Create a CSS file named `ChildComponent.css` in the `src` directory and add the following CSS:

**File:** `src/ChildComponent.css`

```css
.data-item {
  margin-bottom: 20px;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 4px;
}
```

### Step 10: Render The Child Component

Add the `ChildComponent` to the page.

1. Import the `ChildComponent` in `App.jsx`.
2. **In the `App` component's return statement**, add the `ChildComponent` as a child of the `ParentComponent`.

**Check:** Ensure the `ChildComponent` renders on the page with Star Wars character data.

Once you've confirmed it works, you've completed the assignment.

### Summary

- You’ve successfully created a React app that fetches data from the Star Wars API and displays it using parent-child component architecture.
- You’ve implemented a Navbar and Sidebar using `props.children`.
- You’ve created a parent component that displays child components.

Congratulations on completing the assignment! Feel free to ask if you need further assistance or have any questions.

### Bonus

1. Add more child components to display data from other endpoints in the Star Wars API.
2. Add a loading spinner to the child components while the data is being fetched.
3. Add "next" and "previous" buttons to the child components to navigate through the data. (Hint: Use the `next` and `previous` properties in the API response.)
4. Add a search bar to the child component to search for a particular person.
