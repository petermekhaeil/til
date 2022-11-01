# Netlify Node.js Version

Netlify uses `nvm` in their build images. Set the Node.js version in `.npmrc` to tell Netlify which version you want to use. Netlify will also cache the downloaded version as a dependency to speed up subsequent builds.

Using the `.npmrc` approach also lets other developers know what version of Node.js is required.
