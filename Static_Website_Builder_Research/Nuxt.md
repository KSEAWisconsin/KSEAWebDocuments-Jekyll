# Nuxt

## Basic Description
-  a framework that builds on top of Vue
-  simplifies the devlopment of universal or single page **Vue apps**

## Feautures
-  Written in **JavaScript**
-  MIT License
-  *Node.js server will be used to deliver HTML based on Vue components to the client instead of the pure Javascript*
-  Universal rendering without the need for a server
   +  can host the app on GitHub Pages or Amazon S3

## Reason for Choosing Nuxt
-  Universal apps : JavaScript code that can execute both on the client and the server side.
   + access to properties (isServer, isClient) to make rendering on the client/ server easier
-  SEO Optimization
   + preload your app on the server which will improve SEO - helps get rid of the blank page
-  Control of head, title, meta, etc
-  Simple page routing
   + can access pages by adding the specific folder name which will be located on given pages folder

## Reason for Refusing Nuxt
-  **Lack of information/explanation about common errors** - time consuming 
-  Need to update certain version for certain browser
   + We cannot force users to update their browser version
-  Recommend advanced knowledge about SSR(Server-Side Rendering)

