[//]: # "This README.md file is auto-generated, all changes to this file will be lost."
[//]: # "To regenerate it, use `python -m synthtool`."
<img src="https://avatars2.githubusercontent.com/u/2810941?v=3&s=96" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# [Google Cloud Text-to-Speech: Node.js Client](https://github.com/googleapis/nodejs-text-to-speech)

[![release level](https://img.shields.io/badge/release%20level-alpha-orange.svg?style=flat)](https://cloud.google.com/terms/launch-stages)
[![npm version](https://img.shields.io/npm/v/@google-cloud/text-to-speech.svg)](https://www.npmjs.org/package/@google-cloud/text-to-speech)
[![codecov](https://img.shields.io/codecov/c/github/googleapis/nodejs-text-to-speech/master.svg?style=flat)](https://codecov.io/gh/googleapis/nodejs-text-to-speech)




Cloud Text-to-Speech API client for Node.js


* [Google Cloud Text-to-Speech Node.js Client API Reference][client-docs]
* [Google Cloud Text-to-Speech Documentation][product-docs]
* [github.com/googleapis/nodejs-text-to-speech](https://github.com/googleapis/nodejs-text-to-speech)

Read more about the client libraries for Cloud APIs, including the older
Google APIs Client Libraries, in [Client Libraries Explained][explained].

[explained]: https://cloud.google.com/apis/docs/client-libraries-explained

**Table of contents:**


* [Quickstart](#quickstart)
  * [Before you begin](#before-you-begin)
  * [Installing the client library](#installing-the-client-library)
  * [Using the client library](#using-the-client-library)
* [Samples](#samples)
* [Versioning](#versioning)
* [Contributing](#contributing)
* [License](#license)

## Quickstart

### Before you begin

1.  [Select or create a Cloud Platform project][projects].
1.  [Enable billing for your project][billing].
1.  [Enable the Google Cloud Text-to-Speech API][enable_api].
1.  [Set up authentication with a service account][auth] so you can access the
    API from your local workstation.

### Installing the client library

```bash
npm install @google-cloud/text-to-speech
```


### Using the client library

```javascript
// Imports the Google Cloud client library
const textToSpeech = require('@google-cloud/text-to-speech');

// Import other required libraries
const fs = require('fs');
const util = require('util');
async function main() {
  // Creates a client
  const client = new textToSpeech.TextToSpeechClient();

  // The text to synthesize
  const text = 'Hello, world!';

  // Construct the request
  const request = {
    input: {text: text},
    // Select the language and SSML Voice Gender (optional)
    voice: {languageCode: 'en-US', ssmlGender: 'NEUTRAL'},
    // Select the type of audio encoding
    audioConfig: {audioEncoding: 'MP3'},
  };

  // Performs the Text-to-Speech request
  const [response] = await client.synthesizeSpeech(request);
  // Write the binary audio content to a local file
  const writeFile = util.promisify(fs.writeFile);
  await writeFile('output.mp3', response.audioContent, 'binary');
  console.log('Audio content written to file: output.mp3');
}

```



## Samples

Samples are in the [`samples/`](https://github.com/googleapis/nodejs-text-to-speech/tree/master/samples) directory. The samples' `README.md`
has instructions for running the samples.

| Sample                      | Source Code                       | Try it |
| --------------------------- | --------------------------------- | ------ |
| Audio Profile | [source code](https://github.com/googleapis/nodejs-text-to-speech/blob/master/samples/audioProfile.js) | [![Open in Cloud Shell][shell_img]](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googleapis/nodejs-text-to-speech&page=editor&open_in_editor=samples/audioProfile.js,samples/README.md) |
| List Voices | [source code](https://github.com/googleapis/nodejs-text-to-speech/blob/master/samples/listVoices.js) | [![Open in Cloud Shell][shell_img]](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googleapis/nodejs-text-to-speech&page=editor&open_in_editor=samples/listVoices.js,samples/README.md) |
| Quickstart | [source code](https://github.com/googleapis/nodejs-text-to-speech/blob/master/samples/quickstart.js) | [![Open in Cloud Shell][shell_img]](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googleapis/nodejs-text-to-speech&page=editor&open_in_editor=samples/quickstart.js,samples/README.md) |
| Synthesize | [source code](https://github.com/googleapis/nodejs-text-to-speech/blob/master/samples/synthesize.js) | [![Open in Cloud Shell][shell_img]](https://console.cloud.google.com/cloudshell/open?git_repo=https://github.com/googleapis/nodejs-text-to-speech&page=editor&open_in_editor=samples/synthesize.js,samples/README.md) |



The [Google Cloud Text-to-Speech Node.js Client API Reference][client-docs] documentation
also contains samples.

## Versioning

This library follows [Semantic Versioning](http://semver.org/).




This library is considered to be in **alpha**. This means it is still a
work-in-progress and under active development. Any release is subject to
backwards-incompatible changes at any time.



More Information: [Google Cloud Platform Launch Stages][launch_stages]

[launch_stages]: https://cloud.google.com/terms/launch-stages

## Contributing

Contributions welcome! See the [Contributing Guide](https://github.com/googleapis/nodejs-text-to-speech/blob/master/CONTRIBUTING.md).

## License

Apache Version 2.0

See [LICENSE](https://github.com/googleapis/nodejs-text-to-speech/blob/master/LICENSE)

[client-docs]: https://googleapis.dev/nodejs/text-to-speech/latest#reference
[product-docs]: https://cloud.google.com/text-to-speech
[shell_img]: https://gstatic.com/cloudssh/images/open-btn.png
[projects]: https://console.cloud.google.com/project
[billing]: https://support.google.com/cloud/answer/6293499#enable-billing
[enable_api]: https://console.cloud.google.com/flows/enableapi?apiid=texttospeech.googleapis.com
[auth]: https://cloud.google.com/docs/authentication/getting-started

<a name="reference"></a>
