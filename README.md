# Sample application for Electron + React workshop


Scaffolding of an Electorn+React App includes two stages:
- generation of React App,
- its extension with Electron.

## Scaffolding of React App

The easiest way to generate a standard React App without going deep into configuration is [create-react-app](https://github.com/facebook/create-react-app).

To start with the first phase type

```
npx create-react-app my-app
cd my-app
```

Having this done you recieve a ready to launch working React Web App. You can try and feel it by launching:

```
npm start
```

## Adding Electron part

To keep things clear a separate folder must be allocated for an Electron App and install Electron:
```
mkdir eApp
npm i -D electron
touch ./eApp/main.js
```
To launch an Electron part along with React the following lines of package.json must be added/replaced:

```json
{
    "main": "./eApp/main.js",
    "scripts": {
        "web": "react-scripts start",
        "electron": "set NODE_ENV=dev&& nodemon --watch * --exec \"electron .\"",
        "dev": "concurrently \"npm run web\" \"wait-on http://localhost:3000 && npm run electron\"",
        "build": "react-scripts build",
        "pack": "electron-builder --dir",
        "test": "react-scripts test",
        "eject": "react-scripts eject"
    }
}
```
as well as [concurrently](https://www.npmjs.com/package/concurrently) and [wait-on](https://www.npmjs.com/package/wait-on) packages must be installed:
```
npm i -D concurrently wait-on
```


Having this done 

### `npm run web` 
	can be used to start React part of the app in browser (with hot-reload),

### `npm run electron` 
	can be used to start Electron part of the app (with hot-reload),

### `npm run dev` 
	starts full application in development mode,

### `npm run build`
	builds the app for production to the `build` folder,	

### `npm run test`
	runs test of the React part of application,	
	
### `npm run pack`
	packs the app in one bundle and creates executive files,	
	
### `npm run eject`
	if you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.
	Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. 
	All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.
	**Note: this is a one-way operation. Once you `eject`, you can’t go back!**
	

*** to be deleted ***	
	
This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br>
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br>
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br>
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (Webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
