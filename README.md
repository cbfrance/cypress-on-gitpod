## Cypress on gitpod

Cypress 13 with e2e tests running on gitpod.io.

## Why

This way you can start up a Cypress instance without running it locally.

This is useful for demonstration purposes and potentially for collaborative cypress UI? 

Warning: This is not a typical way to run Cypress and is likely not fully supported. 

Originally based on [cypress-on-gitpod](https://github.com/mikenikles/cypress-on-gitpod) with upgraded dependencies.

## How does it work?

The Gitpod configuration in `.gitpod.yml` contains the following settings:
* `image`: A custom Docker image to use for the development environment workspace.
* `tasks`: Two terminals, one that install dependencies and starts the development server. The other one that opens Cypress.
* `ports`: Instructions to open port `6080` in a new tab. This is where the Virtual Desktop runs and where you can interact with Cypress.

The `.gitpod.Dockerfile`:
* Uses the `gitpod/workspace-full-vnc` base image, which includes a virtual desktop.
* Installs the required dependencies to run Cypress.
    * This is documented at https://docs.cypress.io/guides/guides/continuous-integration.html#Dependencies.
