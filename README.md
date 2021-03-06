# Numenera-FoundryVTT

Do you enjoy using the system? Then support my harmful caffeine intake habits and buy me some beans!

[![Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://buymeacoffee.com/SolarBear)

## What is this?

This repository is support for various Cypher system roleplaying games for the [Foundry virtual tabletop](http://foundryvtt.com/#about-foundry-virtual-tabletop).

We currently officially support

* [Numenera](http://numenera.com/)
* [The Strange](http://thestrangerpg.com/)
* Soon: generic Cypher System

Don't know about them? Check them out!

## Features

See a mostly complete tour here: https://www.youtube.com/watch?v=yiK2A3iq8gY

* Sheets for PCs, NPCs, skills, cyphers... anything under the 9th World's sun!
* Unidentified numenera items so your players don't know what you've given them!
* Numenera items can either have a fixed level or a randomly-generated one from a formula (eg. 1d6+2). Once given to a PC, that level is determined randomly, but the GM may override that value if they wish.
* Players can create their own items or use pre-made ones
* Dice rolls explicitly tell you about minor and major effects, as well as free GM intrusions
* A third health bar for PC tokens

## How do I use it?

To install, simply go to the _Game Systems_ tab of the _Configuration and Setup_ screen, click the _Install System_ button on the lower left; scroll down to _Numenera_ and click Install.

Foundry will download the current bundle and afterwards you only need to create a new world using that system. Easy as pie!

## Can I help?

Of course you can!

First and foremost, use it! Use the system for your games and send any feedback you may have, good or bad, to me either directly through Discord or by creating an issue on Github. Show it to your friends. Broadcast it on national television. Everything helps.

Otherwise, I'm always looking for all kinds of help:

* wiki: this repo has a wiki and it would be a great place to document features and tips!
* translations: any language translations are welcome! Already translated:
    * English
    * French
    * Brazilian Portugese
    * German
* layout: if you have any HTML and CSS skills, you're probably better at this than I am!
* feature development: there's a LOT of work ahead, so if you're familiar with Javascript, there's work to be done

Whatever the case, just get in touch.

## Requests

If you'd like something added or prioritized, just drop me a line! You can easily join me by creating in issue here or through the [Foundry Discord server](https://discordapp.com/invite/DDBZUDf).

## Dev info

If you're a regular user, shoo! This is not your section: you should leave now while you still can. It's scary down there, I tell ya.

If you're the kind of person who knows HTML, CSS and/or Javasript, well 1) my condolences and 2) read on.

### How do I deploy this?

#### Method 1: deploy as is

If you want to use the code as is - unminified, without tree-shaking, etc. - follow these steps.

1. Ensure the Foundry server is installed on your machine.
1. Clone the repo to a directory of your liking using your git client of choice.
1. Open a console and move to that directory.
1. Run `npm install` there. Wait for it to finish.
1. Go to your Foundry data folder and either move your git repo clone into the `worlds/` subdirectory or create a symlink to that directory.
1. Start the Foundry server.
1. Connect to it using your favorite browser.
1. Enjoy.

During developement, just run `npm run watch` to have sass watch over your .sass files and convert them to CSS on the fly. If you mess with the migrations system, make sure to run `npm test` to run the tests.

#### Method 2: deploy an optimized version

First, check the bundling section and follow the steps.

Once you've bundled up the whole thing, unzip the contents of that archive into your `worlds/` subfolder. That's it!

### How do I bundle up the whole thing?

Just run `npm run build`: it uses rollup.js to bundle up everything inside a nice ZIP archive with minified and tree-shaken JS, with all the required JSON, CSS and HTML.

If you add new files that _should_ be added to the bundle (eg. a new HTML template), make sure to add it to the list of files inside rollup.config.js, otherwise it will not be bundled; note this is not necessary for .js files.