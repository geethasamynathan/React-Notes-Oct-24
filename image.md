within the src folder &rarr; create new folder (assets)
Download the image and save in asssets folder

```js
import logo from "./logo.svg";
import "./App.css";
import conceptImg from "../src/assets/react-core-concepts.png";
const reactDescriptions = ["Fundamental", "Intermediate", "advanced"];

function getRandomInt(max) {
  return Math.floor(Math.random() * (max + 1));
}

function Header() {
  const description = reactDescriptions[getRandomInt(2)];
  return (
    <header>
      <img src={conceptImg} alt="concepts image"></img>
      <h1>React essentials</h1>
      <p>
        {description} React concepts we will need almost to create SPA with a
        nice look and feel.
      </p>
    </header>
  );
}

function App() {
  return (
    <div className="App">
      <Header />
      <main>Time to start Conditinal Rendering concepts </main>
    </div>
  );
}

export default App;
```


# react Properties (or) React Props

## Passing Props to a Component
React components use props to communicate with each other. Every parent component can pass some information to its child components by giving them props. Props might remind you of HTML attributes, but you can pass any JavaScript value through them, including objects, arrays, and functions.

create components folder in src &rarr; add new file (avatar.jsx)
```js
import React from "react";

function Avatar() {
  return <img src="https://plus.unsplash.com/premium_photo-1731966051195-a1bf3db6487e?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxmZWF0dXJlZC1waG90b3MtZmVlZHwxNXx8fGVufDB8fHx8fA%3D%3D" alt="sample avatar" height={100} width={100} />;
}

export default function Profile() {
  return (
    <>
      <Avatar />
    </>
  );
}

```

 ## App.js
 ```js
import logo from "./logo.svg";
import "./App.css";
import conceptImg from "../src/assets/react-core-concepts.png";
import Profile from "./components/avatar";

const reactDescriptions = ["Fundamental", "Intermediate", "advanced"];

function getRandomInt(max) {
  return Math.floor(Math.random() * (max + 1));
}

function Header() {
  const description = reactDescriptions[getRandomInt(2)];
  return (
    <header>
      <Profile />
      {/* <img src={conceptImg} alt="concepts image"></img> */}
      <h1>React essentials</h1>
      <p>
        {description} React concepts we will need almost to create SPA with a
        nice look and feel.
      </p>
    </header>
  );
}

function App() {
  return (
    <div className="App">
      <Header />
      <main>Time to start Conditinal Rendering concepts </main>
    </div>
  );
}

export default App;


 ![alt text]({58E8C846-270D-4541-A950-42A67F408ACC}.png)

 Pass props to child component
  ```js
 import React from "react";
import img1 from "../assets/image1.avif";
import img2 from "../assets/image2.avif";
import img3 from "../assets/image3.avif";

function Avatar({ person, size }) {
  return (
    <>
      <p>{person.name}</p>
      <p>{person.imageId}</p>
      <img src={person.imageId} alt={person.name} height={size} width={size} />
    </>
  );
}

export default function Profile() {
  return (
    <>
      <Avatar person={{ name: "person 1", imageId: img1 }} size={150} />
      <Avatar person={{ name: "person 2", imageId: img2 }} size={150} />
      <Avatar person={{ name: "person 3", imageId: img3 }} size={150} />
    </>
  );
}
```

# Another way to send(or) pass data between components using props

create another file in src data.js
```js
import reactComponent from "../src/assets/react-components.jpeg";
import reactCoreConcept from "../src/assets/react-core-concepts.png";
import reactProperty from "../src/assets/react-props.jpeg";
import reactJsx from "../src/assets/reaact-jsx.jpeg";

export const CORE_CONCEPTS = [
  {
    image: reactComponent,
    title: "Components",
    description:
      "React Components are the building blocks of ReactJS application. They help to break the user interface into smaller, reusable chunks, making the code easier to manage and maintain. Components can be class-based or function-based, and each type plays an important role in building dynamic and interactive web applicatio",
  },
  {
    image: reactProperty,
    title: "Props",
    description:
      "In ReactJS, the data can be passed from one component to another component using these props, similar to how the arguments are passed in a function.",
  },
  {
    image: reactCoreConcept,
    title: "CoreConcepts",
    description: `The building blocks of a React application's UI, components can be as simple as a button or as complex as an entire app. Components are reusable and can be defined and combined to form larger components.`,
  },
  {
    image: reactJsx,
    title: "JSX",
    description:
      "JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React",
  },
];
```

 create another file CoreConcepts.jsx
 ```jsx
 import React from "react";

export default function CoreConcept({ title, image, description }) {
  return (
    <li>
      <img src={image} alt={title}></img>
      <h3>{title}</h3>
      <p>{description}</p>
    </li>
  );
}
```

# app.jsx
```jsx
import logo from "./logo.svg";
import "./App.css";
import conceptImg from "../src/assets/react-core-concepts.png";
import Profile from "./components/avatar";
import CoreConcept from "./components/corecocepts";
import reactComponent from "./assets/react-components.jpeg";
import { CORE_CONCEPTS } from "./data";

const reactDescriptions = ["Fundamental", "Intermediate", "advanced"];

function getRandomInt(max) {
  return Math.floor(Math.random() * (max + 1));
}

function Header() {
  const description = reactDescriptions[getRandomInt(2)];
  return (
    <header>
      <main>
        <section>
          <h2>Core concepts</h2>
          <ul>
            <CoreConcept
              title={CORE_CONCEPTS[0].title}
              image={CORE_CONCEPTS[0].image}
              description={CORE_CONCEPTS[0].description}
            />
            <CoreConcept
              title={CORE_CONCEPTS[1].title}
              image={CORE_CONCEPTS[1].image}
              description={CORE_CONCEPTS[1].description}
            />
            <CoreConcept {...CORE_CONCEPTS[2]} />
            <CoreConcept {...CORE_CONCEPTS[3]} />
          </ul>
        </section>
      </main>
    </header>
  );
}

function App() {
  return (
    <div className="App">
      <Header />
      <main>Time to start Conditinal Rendering concepts </main>
    </div>
  );
}

export default App;
```