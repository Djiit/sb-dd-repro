# How to reproduce

```bash
npm i
NODE_OPTIONS="-r dd-trace/ci/init" DD_ENV=ci DD_SERVICE=my-javascript-app npm run test-storybook
```

Should throw:

```
(...)
 FAIL   browser: chromium  src/stories/Header.stories.ts
  ● Test suite failed to run

    TypeError: Cannot read properties of undefined (reading 'testPath')

      at new DatadogEnvironment (node_modules/dd-trace/packages/datadog-instrumentations/src/jest.js:118:49)
      at new PlaywrightEnvironment (node_modules/jest-playwright-preset/lib/PlaywrightEnvironment.js:61:13)
      at new CustomEnvironment (node_modules/@storybook/test-runner/playwright/custom-environment.js:5:1)
(...)
```
