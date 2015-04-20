# grunt-download-electron

Grunt tasks for downloading electron, and the compatible version of `chromedriver`.

## Installation

Install npm package, next to your project's `Gruntfile.js` file:

```sh
npm install --save-dev grunt-download-electron
```

Add this line to your project's `Gruntfile.js`:

```js
grunt.loadNpmTasks('grunt-download-electron');
```

## Options

* `version` - **Required** The version of electron you want to download.
* `outputDir` - **Required** Where to put the downloaded electron.
* `downloadDir` - Where to find and save cached downloaded electron.
* `symbols` - Download debugging symbols instead of binaries, default to `false`.
* `rebuild` - Whether to rebuild native modules after electron is downloaded.
* `apm` - The path to apm.
* `token` - The [OAuth token](https://developer.github.com/v3/oauth/) to use for GitHub API requests.

### Usage

Add the necessary configuration to your `Gruntfile.js`:

```js
module.exports = function(grunt) {
  grunt.initConfig({
    'download-electron': {
      version: '0.20.3',
      outputDir: 'my-dependencies'
    }
  });
};
```

or your `Gruntfile.coffee`:

```coffee
module.exports = (grunt) ->
  grunt.initConfig
    'download-electron':
      version: '0.20.3'
      outputDir: 'my-dependencies'
```

Then you can download electron to the path you specified:

```shell
$ grunt download-electron
```

If you're doing selenium-testing of your electron app, you'll need `chromedriver`, which is distributed with electron. To download it into the electron directory:

```shell
$ grunt download-electron-chromedriver
```
