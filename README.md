# (Deprecated) React Standalone Template
Project is deprecated due to the inability to import modules that simply do import statements: import React from 'react'; and export function names directly without giving a namespace: export { functionName }. 

In my attempts to fix these, I discovered additional Babel Standalone attributes to apply to html elements (data-type="module"), which allows for import statements directly inline. However I discovered that some modules imported their own libraries which caused an error called a bare-specifier (paths to modules must be relative). To fix this, you add the babel attribute: data-plugins="transform-modules-umd". This suppressed the messages. But in the case of modern (6.3) react router dom, it also exported all functions directly without a namespace. While not a problem normally (use {} import), when specifying transform-modules-umd it prevents render from working. And when I tried to spit up the react-router-dom module from the others, it was no longer in the global namespace and could not be used. 

Even when I DID put it in the global namespace, the render ceases to work again.

Archiving this project until further developments are made, or someone suggests any possible edits.

## What is this?
This is a webpage that utilizes a few different technologies to become a standalone website application. It uses Bootstrap for simple style and design, Babel so you can use native ES6+ and JSX for your code, React for a rich user and development experience, React Router so you can have a multi-page website, JQuery and PopperJS for Bootstrap features, the React Bootstrap components to make life easier, and Ace Editor/React Ace component for the fancy example page.

Of course, you don't have to use Bootstrap, or React Router, or React Boostrap in your application. I am simply using them as a means to an end for this example. The primary purpose is to have an all in one React example that you can use the latest ecmascript and JSX via Babel conversion. And there inlies the primary purpose; all in one. No external files, just a single HTML file that pulls in resources to make your app work.