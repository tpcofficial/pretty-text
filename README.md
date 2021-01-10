*As of right now, this is the first and last release. This respository is likely to be archived and is not expected to be maintained*

# pretty-text

A simple, small utility for coloured console logging

## Usage

```js
const log = require('pretty-text');

log.info('Hi!');
log.error('Oh no!');
...

//What options are there/
console.info(JSON.stringify(log)); //Shows all variants
```

## Why

This was whipped up in a few seconds for a project we were working on where we didn't need to log to a local file as the service was handling that.

While running in a development environment we wanted to make certain things pop out, so we made a universal NJS module to help along the way to avoid having to replicate the same thing.

## Will this be maintained and have features added

As of right now, no.

This was simply a quick thing I threw on NPM for people to use if they wanted, it's not a maintained package.

If I decided to maintain it I may add:

- Logging to files (false by default)
- Adding custom colours
- Only logging if an environment variable is enabled
- Simple, basic config to allow customisation of features.

## What if I don't want to see this in a production environment

I recommend adding an if statement to just check `if` an environment variable exists.

```js
const log = {
    info: text => {if (process.env.SOME_ENV_VAR) {console.info(`${col.background.blue + col.foreground.white}[i] ${text}${col.reset + col.reset}`)}},
    error: text => {if (process.env.SOME_ENV_VAR) {console.warn(`${col.background.red + col.foreground.white}[e] ${text}${col.reset + col.reset}`)}},
    success: text => {if (process.env.SOME_ENV_VAR) {console.info(`${col.background.green + col.foreground.white}[s] ${text}${col.reset + col.reset}`)}},
    warn: text => {if (process.env.SOME_ENV_VAR) {console.warn(`${col.background.white + col.foreground.red}[w] ${text}${col.reset + col.reset}`)}},
    request: text => {if (process.env.SOME_ENV_VAR) {console.log(`${col.background.black + col.foreground.yellow}[r] ${text}${col.reset + col.reset}`)}}
};
```

## The name 'pretty-text'

Hi jessica (pretty-text) <3
