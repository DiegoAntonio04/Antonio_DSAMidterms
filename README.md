# React JS Starter Project<h1>

This is a simple React JS project to help you get started with React development.

## What is React JS?
React JS is an open-source JavaScript library for building user interfaces, especially single-page applications. It allows developers to create reusable UI components and manage state efficiently.

______________________________________________________________________________________________________________________

## Prerequisites
Before setting up the project, ensure the following are installed on your machine:
- **Node.js** and **npm**  
  Download and install from [https://nodejs.org/](https://nodejs.org/).

Verify installation:
  bash
  
  node -v
  npm -v

## Setup Instructions

### Option 1: Using Create React App (Recommended for Beginners)
1.Create a new React app:
  bash

  npx create-react-app my-app

Note:Replace my-app with your desired project name.

2.Navigate to the project directory:
  bash

  cd my-app

3.Start the development server:
  bash
  npm start

### Option 2: Manual Setup (For Advanced Users)
1.Create a project directory:

  bash

  mkdir my-react-app
  cd my-react-app
  
2.Initialize npm:

  bash

  npm init -y

3.Install React and React DOM:

  bash

  npm install react react-dom

4.Install Babel and Webpack:

  bash

  npm install --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader webpack webpack-cli webpack-dev-server
5.Create the required configuration files:

-.babelrc:

  json


  {
    "presets": ["@babel/preset-env", "@babel/preset-react"]
  }

-webpack.config.js:

  javascript

  const path = require('path');

  module.exports = {
    entry: './src/index.js',
    output: {
      path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js',
    },
    module: {
      rules: [
        {
          test: /\.(js|jsx)$/,
          exclude: /node_modules/,
          use: {
            loader: 'babel-loader',
          },
        },
      ],
    },
   devServer: {
      contentBase: path.join(__dirname, 'dist'),
      compress: true,
      port: 3000,
    },
  };

6.Set up project structure:

-src/index.js:

  javascript

    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './App';

    ReactDOM.render(<App />, document.getElementById('root'));

-src/App.js:

  javascript
  
  import React from 'react';

  function App() {
    return <h1>Hello, React!</h1>;
  }

  export default App;

7.Create an HTML template:

-public/index.html:

html

  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>React App</title>
  </head>
  <body>
    <div id="root"></div>
    <script src="../dist/bundle.js"></script>
  </body>
  </html>

8.Run the development server:

  bash

  npx webpack serve --mode development

### Running the Project
-Create React App:
Use npm start to start the development server.

-Manual Setup:
Use npx webpack serve --mode development to run the Webpack dev server.