#Design Documentation

Parity is a number puzzles game written in JavaScript. This document is to provide the technical documentation for how each of it's components can interact with each other

##Core(core.js)
This game is run by a core engine which contains the mediator and potentially some subscriptions to other components

##Modules
Each of the separate components is this game is distributed as a *module* and has it's own namespace. These are the following modules that currently exist

- BoardModule(board.js)
- ControlModule(controls.js)
- CookieDataModule(cookiedata.js)
- GameModule(game.js)
- LoaderModule(loader.js)
- OverlayModule(overlay.js)
- StoryModule(story.js)

###ControlModule
The ControlModule is going to handle input from the user.

**Subscribed**: (none)

**Published**:

- controls_key_enter
- controls_key_space
- controls_key_left
- controls_key_up
- controls_key_right
- controls_key_down

###CookieDataModule
The CookieDataModule handles saving and loading the game's progress by means of cookies. It also handles reading the hash of the page url and (hopefully soon)
will handle the updating of the hash as well

**Subscribed**:

- cookie_data_save
- cookie_data_load

**Published**:

- cookie_data_save_complete
- cookie_data_load_complete


###LoaderModule
The LoaderModule is special, it's loaded directly by the core and handles the
loading of all the modules that follow as well as loads the story.

**Subscribed**:

- loader_load_modules
- loader_modules_loaded
- story_story_loaded

**Published**:

- loader_modules_loaded
- story_get_story

###GameModule