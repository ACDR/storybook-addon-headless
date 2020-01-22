# Contributing

## Getting Started

#### Install

```sh
npm install
```

This will wipe any existing `node_modules` folder and dependency lock files and do a fresh install of all dependencies.

#### Start

```sh
npm run start
```

This first remove any existing generated folders and then will run [Rollup](https://github.com/rollup/rollup) in watch mode and then start the [Storybook](https://github.com/storybookjs/storybook) dev server. Changes to addon files will take a few seconds to be recompiled into the `dist` folder which may also kick off a webpack recompile for Storybook. You will need to refresh the browser after the console reads:

```sh
created dist\register.js in [N]s

[DateTime] waiting for changes...
```

#### Commit

```sh
npm run commit
```

This will:

-   Lint the entire project
-   Run [Git's Interactive Staging](https://git-scm.com/book/en/v2/Git-Tools-Interactive-Staging) to select the files to commit
-   Run [Prettier](https://github.com/prettier/prettier) on all staged files
-   Run [Git CZ](https://github.com/streamich/git-cz) for semantic commit messages

It is important to use this method of committing to maintain code cleanliness, project history, and to release version updates correctly. There is also a mechanism in place to validate commit messages, so it's possible that you'll run into issues trying to commit using a different method.

#### Upgrade

```sh
npm run upgrade
```

This will run [NPM Check](https://github.com/dylang/npm-check) in interactive mode. Dependencies and Dev-dependencies will be upgraded and saved with the expected exactness. Be careful to test functionality after running this command.

Dev-dependencies should be installed with an exact version.

Dependencies should be installed with a `^`.

#### Resources

Because documentation is not extensive, having to read through Storybook addons and libs source code is necessary:

-   [https://storybook.js.org/docs/addons/writing-addons/](https://storybook.js.org/docs/addons/writing-addons/)
-   [https://storybook.js.org/docs/addons/api/](https://storybook.js.org/docs/addons/api/)
-   [https://github.com/storybookjs/storybook/tree/next/addons](https://github.com/storybookjs/storybook/tree/next/addons)
-   [https://github.com/storybookjs/storybook/tree/next/lib/addons](https://github.com/storybookjs/storybook/tree/next/lib/addons)
-   [https://github.com/storybookjs/storybook/tree/next/lib/api](https://github.com/storybookjs/storybook/tree/next/lib/api)
-   [https://github.com/storybookjs/storybook/tree/next/lib/components](https://github.com/storybookjs/storybook/tree/next/lib/components)

It should also be noted that not all available tools will work everywhere. For example, React hooks from the `@storybook/addons` library will not function on the decorator, but should be used on the panel. It's not always clear when and where things will work so it requires a certain amount of trial and error. Please add to these notes on discovered quirks or undocumented restrictions/features.
