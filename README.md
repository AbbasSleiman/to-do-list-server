# To-Do List Server

## Overview

This Node.js API handles the account and storage side of a personal task manager. It gives the React client endpoints for sign-up, sign-in, session checks, and task management. Express uses the session to identify the signed-in user, and the data layer connects to Azure SQL through Tedious, with database credentials retrieved through Azure Key Vault.

## How it’s built

- **Account and task endpoints.** [The Express entry point](src/index.js) wires up session handling and routes for listing, creating, editing, and deleting tasks.
- **Database integration.** [Database queries](src/database/queries.js) and [connection setup](src/database/connection.js) sit apart from the HTTP routes.
- **Companion frontend.** [To-Do List Client](https://github.com/AbbasSleiman/to-do-list-client) contains the React screens for accounts and tasks.

## Run or explore locally

Install dependencies with `npm install`. For a working instance, point the connection and [Key Vault integration](src/azure_keys.js) at your own Azure resources, provide an identity with access to the vault, and prepare the tables used by the queries. Start the server with `npm start`. It defaults to port `8080`.
