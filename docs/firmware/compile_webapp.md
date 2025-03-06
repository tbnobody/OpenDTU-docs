# Compile WebApp

## General information

The WebApp works completely independent of the C/C++ firmware. When compiling
the firmware, the pre-compiled WebApp will be embedded into the firmware `.bin`
file. The communication between the frontend and the ESP is just done using the
Web API.

If you've changed the WebApp, you have to (re-)compile the WebApp before building the firmware.

There is also a dev server which hosts the frontend at your local computer and
allows a easy development. It will forward all the requests to the backend
automatically to your ESP. That means you can develop the webinterface without
flashing the ESP (if the Web API stays the same).

## Install prerequisites

You need to install [NodeJS LTS](https://nodejs.org/en/download/){target=_blank} to be able to work with the WebApp.

## Building the WebApp

The WebApp will be build using `yarn`. First of all you have to install all the
dependencies. Afterwards the app will be built. Start a Terminal of your choice
and enter the following commands:

```bash
cd webapp
yarn install
yarn build
```

The generated WebApp will be placed in the `webapp_dist` directory from where it gets included by PlatformIO.

## Starting the Development Server

First of all, create a file called `vite.user.ts` in the `webappp` directory with the following content:

```ts
export const proxy_target = '192.168.20.110'
```

Replace the IP with the IP of your ESP.

To start the development server execute the following commands:

```bash
yarn dev
```

## Lint with [ESLint](https://eslint.org/)

```bash
yarn lint
```

## Format Source Code

Automatically format the source code files to use a common format before committing changes.

```bash
yarn format
```
