# Complete Guide to Creating a Web Application with Vite, React, and Tailwind CSS

Follow these steps to quickly set up a modern and efficient development environment.

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Creating the Project with Vite](#creating-the-project-with-vite)
4. [Installing React Router](#installing-react-router)
5. [Setting Up Tailwind CSS](#setting-up-tailwind-css)
6. [Project Structure](#project-structure)
7. [Creating Components and Pages](#creating-components-and-pages)
8. [Setting Up Routes with React Router](#setting-up-routes-with-react-router)
9. [Starting the Development Server](#starting-the-development-server)
10. [Conclusion](#conclusion)

## Introduction

In this guide, you will learn how to set up a modern web application using **Vite**, **React**, and **Tailwind CSS**.  
Vite offers a fast and efficient development environment, React makes it easy to build dynamic user interfaces,  
and Tailwind CSS provides a flexible and efficient way to design styles.

## Prerequisites

Before getting started, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (version 12 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

You can verify the installation by running the following commands in your terminal:

```bash
node -v
npm -v
```

## Creating the Project with Vite

Vite simplifies the configuration of React projects. Below are two options: one for JavaScript projects and another for TypeScript projects.

1. Run the following command to create a new project:
   
   ```bash
   npm create vite@latest project-name
   ```

2. During the setup, you will be prompted to **select a framework**. Choose **React**.

3. Next, you will be asked to **select a variant**. Choose **JavaScript** or **TypeScript**, depending on your preference.

4. Navigate to your project folder:

   ```bash
   cd project-name
   ```

5. Install the dependencies:

   ```bash
   npm install
   ```
   
## Installing React Router

To enable navigation between pages, install React Router by running the following command:

```bash
npm install react-router-dom
```

This will allow you to define and manage routes within your application.

## Setting Up Tailwind CSS

```bash
npm install -D tailwindcss@3.3.3 postcss autoprefixer
npx tailwindcss init -p
```

Modify `tailwind.config.js`:

```/** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: { extend: {} },
  },
  plugins: [],
};
```

Add Tailwind directives in `src/index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Project Structure

```
project-name/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx (or Navbar.tsx)
│   ├── pages/
│   │   ├── Home.jsx (or Home.tsx)
│   │   ├── About.jsx (or About.tsx)
│   ├── App.jsx (or App.tsx)
│   ├── main.jsx (or main.tsx)
│   └── index.css
├── index.html
├── package.json
└── tailwind.config.js
```

## Creating Components and Pages

Example `Navbar.tsx`:

```tsx
import { Link } from "react-router-dom";

const Navbar = () => (
  <nav className="bg-gray-800 p-4">
    <ul className="flex space-x-4">
      <li><Link to="/">Home</Link></li>
      <li><Link to="/about">About</Link></li>
    </ul>
  </nav>
);
export default Navbar;
```

## Setting Up Routes with React Router

```tsx
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Navbar from "./components/Navbar";
import Home from "./pages/Home";
import About from "./pages/About";

const App = () => (
  <Router>
    <Navbar />
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  </Router>
);
export default App;
```

## Starting the Development Server

```bash
npm run dev
```

Access `http://localhost:5173`.

## Conclusion

Now you have a fully configured application with **Vite**, **React**, and **Tailwind CSS**, featuring functional routing and a modular structure ready to scale.  
This guide was designed to streamline web development. Created by **PixlGalaxy**. 🚀
