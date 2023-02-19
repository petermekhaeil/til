# Module Federation

Module Federation is a microfrontend pattern that involves 2 components:

## Remote

- Remote apps expose modules for other microfrontends apps to import. 
- Remote apps are compiled and deployed independently. 
- Remote apps expose an entry file that contains the exposed modules.

## Host

- Host app consumes modules exposed from remote apps. 
- The host app owns a module registry that maps the module names with the remote location. 
- The remote modules are imported dynamically on-demand when requested. 

Both [Webpack](https://webpack.js.org/concepts/module-federation/) and [Vite](https://github.com/originjs/vite-plugin-federation) support Module Federation.
