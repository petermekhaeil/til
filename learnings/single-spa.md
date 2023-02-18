# Microfrontend using single-spa

[single-spa](https://single-spa.js.org/) is a JavaScript framework that enables you to develop applications using multiple frontend frameworks.

Components involved in single-spa:

- **root-config**: Entry point for the microfrontend application. It registers the applications and configured the router rules to decide which application should be rendered for each specific route.
- **application**: Self-contained application developed using any front-end application. They are packaged as modules. 
