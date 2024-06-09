# <img src="https://github.com/sssshefer/d-keeper/assets/63253440/051bcdeb-1af3-417f-b1fe-e991ba1494e5" width="32"> D-Keeper: A Decentralized Notes on the Internet Computer

## Table of Contents
- [Introduction](#introduction)
- [Theory Notes](#theory-notes)
  - [Internet Computer](#internet-computer)
  - [DFX](#dfx)
- [Features and Functionality](#features-and-functionality)
- [Implementation](#implementation)
  - [Backend Code](#backend-code)
  - [Frontend Code](#frontend-code)
- [Running the Project Locally](#running-the-project-locally)

## Introduction
D-Keeper is a decentralized application (dApp) created to learn and demonstrate the capabilities of the Internet Computer (IC) blockchain. This application simulates a simple notes keeper where users can create, keep and delete notes

## Theory Notes

### Internet Computer
The Internet Computer is a blockchain that runs at web speed with unbounded capacity. It aims to extend the functionality of the public internet so that it can host backend software, transforming it into a global compute platform. Key features include:
- **Canisters**: Smart contracts on the Internet Computer that combine code and state.
- **Cycles**: The fuel that powers computation in the Internet Computer.
- **Motoko**: A programming language designed for the Internet Computer.

### DFX
DFX is the command-line tool used to manage, deploy, and interact with canisters on the Internet Computer. Key commands include:
- `dfx start`: Starts the local replica.
- `dfx new <project-name>`: Creates a new project.
- `dfx deploy`: Deploys the canisters.
- `dfx canister call <canister-name> <method-name>`: Calls a method on a canister.

To learn more before you start working with `dbank2`, see the following documentation available online:
- [Quick Start](https://internetcomputer.org/docs/current/developer-docs/setup/deploy-locally)
- [SDK Developer Tools](https://internetcomputer.org/docs/current/developer-docs/setup/install)
- [Motoko Programming Language Guide](https://internetcomputer.org/docs/current/motoko/main/motoko)
- [Motoko Language Quick Reference](https://internetcomputer.org/docs/current/motoko/main/language-manual)

## Features and Functionality
- **Create note**: Allows users to create a new note with title and content
- **Keep notes**: Enables users to save the notes even after reloading the webpage or deploying the application again
- **Delete notes**: Users can request to delete notes, and the changes will be saved upon the next launch of the app

## Implementation

### Backend Code
The backend canister is written in Motoko and manages the core operations with notes
### Frontend Code
The frontend is a simple HTML page built with React for handling user input and communicating with the backend

## Running the Project Locally

If you want to test your project locally, you can use the following commands:

```bash
# Starts the replica, running in the background
dfx start --background

# Deploys your canisters to the replica and generates your candid interface
dfx deploy
```

Once the job completes, your application will be available at `http://localhost:4943?canisterId={asset_canister_id}`.

If you have made changes to your backend canister, you can generate a new candid interface with

```bash
npm run generate
```

at any time. This is recommended before starting the frontend development server, and will be run automatically any time you run `dfx deploy`.

If you are making frontend changes, you can start a development server with

```bash
npm start
```

Which will start a server at `http://localhost:8080`, proxying API requests to the replica at port 4943.

