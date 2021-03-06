
# FullCalendar Vue Component Contributor Guide

Information for people wanting to contribute code to this project.


## Build Commands

Look in `package.json` to see all available build scripts, the most important being:

```bash
npm run build
npm run watch # continusouly build
npm run test # continuously test
npm run dist # build everything necessary for the NPM package
```

## Before Submitting

Before submitting a PR, make sure testing and linting pass:

```bash
npm run test-single
npm run lint
```

Also, make sure the [example project] builds correctly with the new code. To test, use [npm link] to trick it into using your not-yet-published dist files.


## Publishing

For publishing to NPM/Github, run something like this:

```bash
./scripts/version 9.9.9 # build and stage the release
./scripts/publish 9.9.9 # publish to verdaccio (local npm server)
./scripts/publish 9.9.9 --production # publish to npm, push to github
```

This will create a detached+tagged release commit.


## Dependency Quirks

The `@types/estree` package is not explicitly used by this repo. It is a transitive dependency with two competing versions.


[example project]: https://github.com/fullcalendar/fullcalendar-example-projects/tree/master/vue
[npm link]: https://docs.npmjs.com/cli/link.html
