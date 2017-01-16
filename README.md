# chat
Basic JS Chat

Current Design Thoughts:
https://app.moqups.com/justin.jennissen@gmail.com/KY6oB58mek/view

Please find below some suggestions on how to start and proceed. By no means do you need to follow these or even read them. Just thought I'd jot some stuff down to give you a central starting point in case that is desirable.

# Install Node and NPM

NodeJS is a powerful server side engine and web server which uses the JavaScript language primarily. If you're on a Linux Machine or a Mac (Unix Machine), you'll want to be sure you install the "sudo-less" version so that it does not require admin credentials to install any packages. Check out [this tutorial](https://johnpapa.net/how-to-use-npm-global-without-sudo-on-osx/) for OSX. Windows you're on your own, but I'm guessing it's not even an issue on windows machines.

# Setup a simple Node server

## Init Node
Initialize a node project with npm using NPM's init command from the command line (while in the project directory).
You will get a series of prompts asking about project information. Most can just use the default values (just hit enter).

```shell
npm init
```

You will now see a `package.json` file in the project. This is the NPM definition of the project.
It will also control all the NPM dependencies for the project, the project / application version,
some specific application commands, etc..

Many tutorials will start with setting up the node project to varying degrees. Once it's done, you don't need to do it again.

## Add Express dependency

Using NPM, add the node module `express` as a dependency.

```shell
npm install express --save
```

The `--save` flag will add express as a dependency within the `package.json` file. This allows for easy package
installation by other developers, as well as dependency tracking for the project.

## Create and serve static HTML page using Express

* Make a directory called `content/static`. Inside that folder, create an html file (`index.html` or whatever you want).
* Add some html content to the page. If you want to feel like you know nothing about web development, and like you'll never know everything, check out [HTML5 Boilerplate](https://github.com/h5bp/html5-boilerplate). It basically sets up a bunch of the files and structure you'll need to account for like ALL scenarios. You'll have to google basically every file inside the /dist folder (I still don't know what most of it's for).
* Tell Express to statically serve the content/static directory. Reference [this documentation](http://expressjs.com/en/starter/static-files.html).
* Try making an alias for the folder! (They call it a mount path in the docs)

# Start building the app

## Start chat with Socket.io

Socket.io has a [simple tutorial](http://socket.io/get-started/chat/) on their site for creating a basic chat app using socket.io and ExpressJS. Try it out.

## Get More Advanced

 **Note**: Don't forget, just about anything you want to use should be considered a dependency and thus be added by a package dependency manager (NPM). In case the package isn't obvious on a product's website, just go to https://npmjs.org and do a search.

* Checkout the homework section of the tutorial.
* Incorporate a front-end framework for the client ([Angular](https://angularjs.org/), [Angular 2](https://angular.io/), [React](https://facebook.github.io/react/), [Knockout](http://knockoutjs.com/), something like that), to handle DOM interactions, handle incoming and outgoing messages from/to socket.io.
* Drawup a simple wireframe of how the application should be layed out. Sign up for something like [moqups](https://moqups.com/) or just use pen and paper.
* Build some sweet UI and animations (animated chat bubbles, user list, crazy fonts, etc). Consider a framework (Bootstrap or a [Material Design implementation](https://www.sitepoint.com/top-5-material-design-frameworks-use-2015/)) and be sure to read up on [CSS3 transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions).
* Unit Tests!!! Will likely want to decouple the business functionality (message processing, user operations, etc) from the messaging itself (Socket.io) for easier and more modularozed testing. Checkout [Mocha and Chai](https://www.codementor.io/nodejs/tutorial/unit-testing-nodejs-tdd-mocha-sinon). Look around for tutorials you like, but I'd recommend sticking with Mocha with Chai. Mocha is a testing framework, providing you easy ability to build and run and organize tests (it's like the house walls and furnace and roof, etc). Chai is an assertion library, meaning it comes with all the functions you'd use inside the actual tests to say "this should be happening" or "I expect this to happen, and not that" (it's like the furnishings and decorations and things that are unique to you). A testing home isn't complete without both.
* Think about templating the chat page and compiling it with all the user specific information already in the page to avoid some typical Single Page Application logic to populate those types of relatively static elements. Something like [Handlebars](http://handlebarsjs.com/) or [Pug](https://github.com/pugjs/pug) (formerly Jade).
* Add a database like [MongoDB](https://www.mongodb.com/) to store user information and chats that a user has been involved in. Think about how to modal the user data and chat data and how to tie the two together based on some common shared key.

Pro Tips:
* Find good tutorials for whatever technology you're considering. Give the tutorial a read through or at least a scan through before doing what it's actually teaching. If it's not giving you the level of information you'd like, find another one. Be aware of old tutorials.
* Don't just read about technology, read about concepts that underly the use-case for that technology. Example: don't just google something like "Modally user data in MongoDB", rather google that and compare with "Modeling User data in NOSQL db" or even "database modeling user data". Google "JavaScript design patterns" along with "How to write an Angular Service". Google "TDD" along with "mocha chai tutorial".
* Find other projects that are doing what you're trying to do and read their source code (especially their unit tests).
* Take nothing you read for granted. Don't be a copy/paste developer. Make sure you know how and why what you're pasting actually works. This will bring you down some rabbit holes but that's ok.
* Don't worry about remembering everything. I certainly don't remember everything. Keep well organized bookmarks of anything you read that you like.
* When trying to chose a tool/library/framework or learn about it, search google for the name of the prodect plus "vs" then let Googles auto complete do it's thing. Will open you up to new tools and let you know how they stack up. Ex: google "Angular 2 vs" or "MongoDB vs", then select the top one or two autocomplete suggestions.
