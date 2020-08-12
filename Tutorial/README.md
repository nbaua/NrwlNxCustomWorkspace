## Clone the repository

OR

## Create the workspace

    npx create-nx-workspace@latest

### Enter the following details.

    > Workspace name (e.g., org name) nx-custom
    > What to create in the new workspace empty [an empty workspace with a layout that works best for building apps]
    > CLI to power the Nx workspace Nx [Recommended for all applications (React, Node, etc..)]
    > Use the free tier of the distributed cache provided by Nx Cloud? No [Only use local computation cache]

### Change the prompt to the workspace directory

cd cd nx-custom

### Install the required schematics

`(This is not required with earlier versions, however the latest nx version has issues - https://github.com/nrwl/nx/issues/2953)`

    npm install @nrwl/node
    npm install @nrwl/angular
    npm install @nrwl/nest

### Create the Admin Console Angular App (change the port to 4201)

    nx g @nrwl/angular:app admin-app

    > Which stylesheet format would you like to use? SASS(.scss) [ http://sass-lang.com ]
    > Would you like to configure routing for this application? Yes

### Create the Web Application Angular App (change the port to 4201)

    nx g @nrwl/angular:app web-app

    > Which stylesheet format would you like to use? SASS(.scss) [ http://sass-lang.com ]
    > Would you like to configure routing for this application? Yes

### Create the Server/API Application Angular App (change the port to 4201)

    nx generate @nrwl/nest:application server-app

`Edit the endpoint port of Angular Application by adding port setting under the serve node in workspace.json`

---

## Execute the applications

    nx serve admin-app
    nx serve web-app
    nx serve server-app
