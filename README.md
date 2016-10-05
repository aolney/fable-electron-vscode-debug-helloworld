# fable-electron-vscode-debug-helloworld
A hello world electron app using fable to transpile js and vscode to debug the electron process using source maps

Adapted from 

- [electron-quick-start](https://github.com/electron/electron-quick-start)
- [fable-electron](https://github.com/fable-compiler/fable-electron/tree/master/samples/helloworld)
- [getting started with fable](http://kcieslak.io/Getting-Started-with-Fable-and-Webpack)
- [debug electron apps with vscode](http://code.matsu.io/1)

## What's Electron?

The Electron framework lets you write cross-platform desktop applications using JavaScript, HTML and CSS. It is based on Node.js and Chromium and is used by the Atom editor and many other apps.
> https://github.com/electron/electron

## What's Fable?

[Fable](http://fable.io/) is a F# compiler that emits javascript. In this sample we write code in F#, transpile it appropriately into an Electron app, and then debug that app. 

This is a minimal Electron application based on the [Quick Start Guide](http://electron.atom.io/docs/latest/tutorial/quick-start) within the Electron documentation.

A basic Electron application needs just these files:

- `index.html` - A web page to render.
- `main.fsx` - Starts the app and creates a browser window to render HTML.
- `package.json` - Points to the app's main file and lists its details and dependencies.

You can learn more about each of these components within the [Quick Start Guide](http://electron.atom.io/docs/latest/tutorial/quick-start).

Additionally this sample adds

- `fableconfig.json` - for [fable compiler options](http://fable.io/); tutorial [here](http://kcieslak.io/Getting-Started-with-Fable-and-Webpack)
- `.vscode/launch.json` - for debugging in vscode; tutorial [here](http://code.matsu.io/1)
- `.vscode/tasks.json` - for build/watch tasks; tutorial [here](http://kcieslak.io/Getting-Started-with-Fable-and-Webpack)

## To Use

To clone and run this repository you'll need [Git](https://git-scm.com) and [Node.js](https://nodejs.org/en/download/) (which comes with [npm](http://npmjs.com)) installed on your computer. Some linux distributions call `node` something else, e.g. `nodejs`, which may cause you problems.

To use VSCode you will need to [install it](https://code.visualstudio.com/download).

From your command line:

1. Install fable-compiler 

   * Globally

     `npm install -g fable-compiler`

   * or add this line to package.json
   ```
    "devDependencies": {
       "electron-prebuilt": "^1.2.7",
   ```


2. Clone this repository

   `git clone https://github.com/aolney/fable-electron-vscode-debug-helloworld.git`

3. Build and Run

    * From command line
      1. Go into the repository

         `cd fable-electron-vscode-debug-helloworld`

      2. Run fable (fableconfig.json contains the compiler options)

         `fable`

      3. Run electron

         `npm start`

    * From VSCode
      1. Start VSCode

         `code fable-electron-vscode-debug-helloworld`
      2. Run the build task

         `View -> Command Palette ; type run build task`
      3. Put a breakpoint in main.js or renderer.js
      4. Enter debug mode, select main or render debug dropdown depending on breakpoint location
      5. Run the debugger. Debugger will break at F# line corresponding to the location of your js breakpoint. You may need to `ctrl-r` in Electron to refresh and hit breakpoints in render process, see [here](http://code.matsu.io/1)

#### License [CC0 (Public Domain)](LICENSE.md)
