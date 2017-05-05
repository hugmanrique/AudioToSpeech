# AudioToSpeech
Node.js application that uses Google's Cloud Speech API to convert long audios (up to 80 minutes) to text.

## Google Cloud Setup

First, follow the steps on [cloud.google.com](https://cloud.google.com/speech/docs/getting-started) to set up your project. You will need to create a project, enable the billing (by adding a credit card) and enable the Cloud Speech API for the newly created project.

Once you are done, you will need to create a Cloud Storage segment, which will be the "bucket" where your large audio files will reside. You can create your segment by clicking [here](https://console.cloud.google.com/storage?_ga=1.35831520.1931673077.1494011931).

Finally, you need to generate the credentials for your project. You can do so by clicking [here](https://console.cloud.google.com/apis/credentials). Please note that the Credentials format should be `json` and the type of credential should be a Service Account Key.

Once you've created the key, you need to grant read access to your Cloud Storage segments to read the audio files.

## Actual Setup
Install all the dependencies with `npm install` or `yarn`. Then, build the project (transform ES6 code to ES5 through Babel) with `npm run build` or `yarn run build`.

Next, move the `example.config.json` file into the newly created `dist` folder. Next, modify the `start.sh` file by adding your Google Cloud Credentials you created in the previous steps.

Modify your config values (the audio reference is on the [Google Cloud Docs](https://cloud.google.com/speech/reference/rest/v1/RecognitionConfig)) by specifying the output name and the Cloud Storage URL (gs://).

## Why did you make this?
One of my family relatives is an interviewer, and he asked me for a way to convert a brute audio file into a text file. While this isn't perfect, it made his job much easier.