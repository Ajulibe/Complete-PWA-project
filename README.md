# Complete-PWA-project
This project is extracted from Maxamillian's Course on PWA. Some of the codes are a bit outdated since workbox version 2 is used here, however, it can be combined with the README file added and some code gotten from the workbox documentation


# CREATING A PWA WITH REACT

1) Delete the serviceWorker.js file in the root directory and also in the app.js file import and build the react project.
   This exposes the service-worker.js file as inbuilt by react.
2) After building, Deere the precache manifest file and the assets manifest json file
3) Install serve to serve this built file locally. npm i -g serve .
4) In your terminal, in your root directory, run serve . This will serve all the assets in your build folder as a webpage.

# Now it’s time to cache all the static assets. These include Js,Html,css and static image files.

1) Install work box using npm i workbox-build —save -dev. Note always exclude the service-worker.js file from caching. Look at academinds setup.
   Look back at Maximilian’s course and follow his steps in installation as he worked with firebase.

# NOTE: the service-worker.js file is not to be manually edited with code. Always inject the code for precaching using another file.

1) Notice that Maximilian’s flow is a bit different because we do not have a package.json file to add run scripts.
2) Create file in the root and name it precache.js
   Get content from the PWAhelper.js file which contains the barebones code for injection of precahching code.
3) Change swSrc and swDest to service-worker.js
4) Change the globDirectory to ../build to indicate the build folder.
4) Right now, there is nothing specify that the pwa manifest is injected into the service-worker.js file. To specify this we have to put some helper      code/placeholder in the service-worker.js file.
4) First line will be to import workbox and second line with precahche and route will have (self__WB_manifest)
5) Run node precache.js in the terminal. Check your service-worker.js file. It has been updated with the precached files.

# Note the step of running node precache.js should always be done to effect changes and must be done before your deployment for the update to show.

1) Add a script tag to your index.html and add the logic for registering your service worker. You can google for the latest script or use Maximilian’s own. The   “serviceWorker” in navigator script.
2) Run the node precache script again. It should work well for static assests now on chrome. You can use maximillians approaxh to a indexDB to the project later
