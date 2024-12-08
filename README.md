# portfolio-tailwind-css

To design and develop a personal portfolio website with at least three pages (Home, About, and Contact), using Tailwind CSS for layout and styling, follow these steps:

1. Set Up the React Project:
Start by setting up a new React project using Create React App.

bash
Copy code
npx create-react-app portfolio
cd portfolio
npm start
2. Install Tailwind CSS:
To install Tailwind CSS in your project, follow these steps:

Install the necessary dependencies:
bash
Copy code
npm install -D tailwindcss postcss autoprefixer
Create Tailwind Configuration Files:
bash
Copy code
npx tailwindcss init -p
Configure Tailwind: In tailwind.config.js, ensure the following configuration:
js
Copy code
module.exports = {
  content: [
    "./src/**/*.{html,js,jsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
Include Tailwind in your CSS:
Replace the contents of src/index.css with the following to import Tailwind’s base, components, and utilities:

css
Copy code
/* src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
3. Folder Structure:
Organize your components and pages like this:

css
Copy code
src/
  components/
    Navbar.js
  pages/
    Home.js
    About.js
    Contact.js
4. Create Components and Pages:
Navbar Component (src/components/Navbar.js):
jsx
Copy code
import React from 'react';
import { Link } from 'react-router-dom';

const Navbar = () => {
  return (
    <nav className="bg-blue-600 p-4">
      <ul className="flex justify-center space-x-8">
        <li><Link to="/" className="text-white">Home</Link></li>
        <li><Link to="/about" className="text-white">About</Link></li>
        <li><Link to="/contact" className="text-white">Contact</Link></li>
      </ul>
    </nav>
  );
};

export default Navbar;
Home Page (src/pages/Home.js):
jsx
Copy code
import React from 'react';

const Home = () => {
  return (
    <div className="flex flex-col items-center justify-center p-10">
      <h1 className="text-4xl font-bold mb-4">Welcome to My Portfolio</h1>
      <p className="text-lg text-gray-600">I am a passionate web developer.</p>
    </div>
  );
};

export default Home;
About Page (src/pages/About.js):
jsx
Copy code
import React from 'react';

const About = () => {
  return (
    <div className="flex flex-col items-center justify-center p-10">
      <h1 className="text-4xl font-bold mb-4">About Me</h1>
      <p className="text-lg text-gray-600 max-w-3xl text-center">
        Hi, I'm a web developer with experience in creating dynamic and responsive websites using modern web technologies such as React, JavaScript, and Tailwind CSS.
      </p>
    </div>
  );
};

export default About;
Contact Page (src/pages/Contact.js):
jsx
Copy code
import React from 'react';

const Contact = () => {
  return (
    <div className="flex flex-col items-center justify-center p-10">
      <h1 className="text-4xl font-bold mb-4">Contact Me</h1>
      <form className="w-full max-w-md">
        <input
          type="text"
          placeholder="Your Name"
          className="p-3 mb-4 border border-gray-300 rounded w-full"
        />
        <input
          type="email"
          placeholder="Your Email"
          className="p-3 mb-4 border border-gray-300 rounded w-full"
        />
        <textarea
          placeholder="Your Message"
          className="p-3 mb-4 border border-gray-300 rounded w-full"
          rows="4"
        ></textarea>
        <button
          type="submit"
          className="bg-blue-600 text-white p-3 rounded w-full hover:bg-blue-700"
        >
          Send Message
        </button>
      </form>
    </div>
  );
};

export default Contact;
5. Set Up Routing:
Install react-router-dom to enable navigation between pages:

bash
Copy code
npm install react-router-dom
Then, configure routing in src/App.js:

jsx
Copy code
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Navbar from './components/Navbar';
import Home from './pages/Home';
import About from './pages/About';
import Contact from './pages/Contact';

import './index.css'; // Tailwind CSS

function App() {
  return (
    <Router>
      <Navbar />
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </Router>
  );
}

export default App;
6. Tailwind CSS for Styling and Responsiveness:
Tailwind CSS allows for responsive design out of the box with its utility classes. For example, to make the Navbar responsive:

jsx
Copy code
<nav className="bg-blue-600 p-4">
  <ul className="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-8">
    <li><Link to="/" className="text-white">Home</Link></li>
    <li><Link to="/about" className="text-white">About</Link></li>
    <li><Link to="/contact" className="text-white">Contact</Link></li>
  </ul>
</nav>
This will display the navbar links in a column on small screens and in a row on larger screens (sm:).

7. Run Your Project:
Run the React development server:

bash
Copy code
npm start
Your portfolio website should be live at http://localhost:3000, and you can view the following pages:

Home
About
Contact
Summary:
React Components: Created reusable components for the Navbar and pages (Home, About, Contact).
Tailwind CSS: Applied Tailwind's utility classes for styling and responsiveness.
Routing: Used React Router for navigation between the pages.
