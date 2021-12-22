# puppeteer-google-translate

Translate texts or documents with Google Translate using Puppeteer, deploy on heroku
Fork of original repo: https://github.com/alanleungcn/puppeteer-google-translate

## Installation

```bash
npm i puppeteer-google-translate-heroku
```

## Usage

```js
const { translateText, translateDocs } = require('puppeteer-google-translate');

const opt = { from: 'en', to: 'es', timeout: 10000, headless: true };
// translate from English to Spanish

translateText('text', opt).then((result) => {
	// result: texto
});

translateText(['text', 'array'], opt).then((result) => {
	// result: ['texto', 'formación']
});

translateDocs('txt.txt', opt).then((result) => {
	// result: translated text
});

translateDocs(['txt.txt', 'docx.docx'], opt).then((result) => {
	// result: array of translated text
});
```

## API

### translateText(text, Options)

- `text` \<string | string[]> Text or an array of text to be translated
- returns: Promise<string | string[]>

### translateDocs(path, Options)

- `path` \<string | string[]> Path or an array of path that points to documents
- returns: Promise<string | string[]>
  <br><br>
- `Options` \<Object>
  - `to` \<string> Language to translate to
  - `from` \<?string> Language to translate from. Defaults to `auto`
  - `timeout` \<?number> Time in ms before Puppeteer throws an error, pass `0` to disable timeout. Defaults to `10000`
  - `headless` \<?boolean> Whether to run browser in headless mode. Defaults to `true`

## Disclaimer

This project is only for learning purposes, for Google translation api please check out [the official document](https://cloud.google.com/translate)
