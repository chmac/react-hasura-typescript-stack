react-hasura-typescript-stack
---

Last update: Dec 2019

A skeleton hasura / react setup.

Includes
* typescript
* apollo client
* material UI

## Folders & commands

First, run `yarn` in both the `hasura/` and `frontend/` directories.

* `hasura/`
  - `yarn run hasura` - Start the hasura docker setup
  - `yarn start` - Start the hasura console
* `frontend/`
  - `yarn start` - Standard create-react-app app start

## Config

Config values are set in `.env` files. Several are in the repo.

* `.env` - This is the root config, and is passed to both hasura and frontend via the `env-cmd` package which is included in both `package.json` files both as a devDependency and in the `scripts` part.
* `hasura/.env` - This is read automatically by `docker-compose` in addition to the root `.env` file which is passed in via `env-cmd`.
* `frontend/.env` - This is ready automatically by `create-react-app` in addition to the root `.env/` file which is passed in via `env-cmd`.
  - This supports `env-expand` which means variables in the root `.env` can be made available to the react build like:
    - `REACT_APP_BAR=$FOO`

## Setup

To get started, you need to make the following changes:

- Register an [Auth0](https://auth0.com) account
  - Create an app for it
  - Copy the domain and client id into the root `.env`
