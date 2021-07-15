# Minimal Dnn theme

## Getting started
1. **Important**: This is a template repository, if your intention is to contribute to it, please use the `Fork` button. If your intention is to build a theme using this as a template, please use the `Use this template` button.
2. Clone the repository to the `Portals\_default` folder of a working Dnn site.
3. Navigate to the created folder.
4. You will need `yarn` if you do not have it installed yet, please visit [the yarn website](https://yarnpkg.com/lang/en/).
5. In the command line, run `yarn install` to fetch the dependencies.

## Customizing your theme
To cusomize your theme to your needs, run `yarn settings` and answer a couple of questions.

## Building

1. Run `yarn build` (*You can skip this step if you just ran `yarn settings` since it does it automatically after each setting change*).

## Development
The build scripts have a live-server proxy than will automatically rebuild upon any file change and reload your browser. This is really useful for fast development but has limitations such as not being able to use the persona bar using the proxy.

1. Run `yarn start`.
2. When asked, enter the url of the site you would normally visit.
3. That site will be proxied as http://localhost:3333 and will live-reload unpon any file change.

If you run into cache issues and do not see your changes right away, disable Dnn cache, bundling and minification settings and keep your development panel open. In order to give Dnn time to realize changes, we need to inject a 1 second delay to the reload. If you need more or less delay, it can be adjusted in the `reloadDelay` option of the `browserSync` options. BrowserSync also allows you to view the site in your local network on multiple devices at once and will reload them all! All other BrowserSync options are supported, read [BrowerSync Documentation](https://www.browsersync.io/docs/options) for more details.

## Versioning
This project currently uses manual versioning, please update the version in packages.json to the version you want to release.

## Javascript utilities
In the `scr/scripts/utilities` you will find some useful utilities you can opt into, right now those utilities are:
* `replaceClasses` which takes a list of old>new classes, replace them in content and optionally log that replacement in the browser console.
* There is also a `migrateFa4ToFa5` function that replaces all deprecated FontAwesome4 classes to their best lookalike in FontAwesome5 using the previous `replaceClasses` function. To opt-in into this feature, add the following snipped in the `main.ts` file:
```ts
import { migrateFa4ToFa5 } from './utilities/utils';

document.addEventListener('DOMContentLoaded', () => {
    migrateFa4ToFa5();
});
```