# storybook-raw
An MVP setup of Storybook

## Steps

### `npm i -D storybook`

```
+ storybook@6.3.8
added 725 packages from 294 contributors and audited 725 packages in 32.273s

103 packages are looking for funding
  run `npm fund` for details

found 4 high severity vulnerabilities
  run `npm audit fix` to fix them, or `npm audit` for details
```

### add `storybook` script

`storybook: start-storybook`

```
sh: start-storybook: command not found
npm ERR! code ELIFECYCLE
npm ERR! syscall spawn
npm ERR! file sh
npm ERR! errno ENOENT
npm ERR! storybook-raw@0.0.0 storybook: `start-storybook`
npm ERR! spawn ENOENT
npm ERR! 
npm ERR! Failed at the storybook-raw@0.0.0 storybook script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/chantastic/.npm/_logs/2021-09-22T20_58_44_624Z-debug.log
```

- add `.storybook/main.js`
  - nada
- add package `@storybook/html`

```
+ @storybook/html@6.3.8
added 707 packages from 505 contributors and audited 1432 packages in 44.854s

208 packages are looking for funding
  run `npm fund` for details

found 19 vulnerabilities (13 moderate, 6 high)
  run `npm audit fix` to fix them, or `npm audit` for details
```

```
ERR! Error: No configuration files have been found in your configDir (/Users/chantastic/Documents/GitHub/storybook-raw/.storybook).
ERR! Storybook needs either a "main" or "config" file.
ERR!     at validateConfigurationFiles (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/utils/validate-configuration-files.js:50:11)
ERR!     at loadCustomPresets (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/utils/load-custom-presets.js:19:62)
ERR!     at loadAllPresets (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/presets.js:310:105)
ERR!     at buildDevStandalone (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-server/dist/cjs/build-dev.js:101:48)
ERR!     at async buildDev (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-server/dist/cjs/build-dev.js:154:5)
ERR!  Error: No configuration files have been found in your configDir (/Users/chantastic/Documents/GitHub/storybook-raw/.storybook).
ERR! Storybook needs either a "main" or "config" file.
ERR!     at validateConfigurationFiles (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/utils/validate-configuration-files.js:50:11)
ERR!     at loadCustomPresets (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/utils/load-custom-presets.js:19:62)
ERR!     at loadAllPresets (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-common/dist/cjs/presets.js:310:105)
ERR!     at buildDevStandalone (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-server/dist/cjs/build-dev.js:101:48)
ERR!     at async buildDev (/Users/chantastic/Documents/GitHub/storybook-raw/node_modules/@storybook/core-server/dist/cjs/build-dev.js:154:5)

WARN Broken build, fix the error above.
WARN You may need to refresh the browser.
```

- add `./storybook/main.js`
  - works! ✅
  - get loading screen because there are no stories and no configuration to load them

### Add first story

- add `stories` property to `main.js` export, including paths
  - as soon as we provide a path, we go from a loading state to seeing the error that components couldn't be loaded
  - `"../stories/my-first-story.stories.md"`
- i can't seem to get a single .mdx story to load. trying CSF to see if that works.
  - upon further inspection, looks like mdx functionality might be provided by [Docs](https://storybook.js.org/docs/react/writing-docs/introduction), in essentials


