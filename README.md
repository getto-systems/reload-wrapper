# reload-wrapper

thin wrapper for [alallier/reload](https://github.com/alallier/reload) to launch static web server with live reload from command line

```
$ cat package.json
{
  "scripts": {
    "reload": "reload-wrapper -d ./public -w ./public/dist"
  }
}

$ npm run reload
```


###### Table of Contents

- [Requirements](#Requirements)
- [Usage](#Usage)
- [License](#License)

<a id="Requirements"></a>
## Requirements

- alallier/reload: ^2.3.1


<a id="Usage"></a>
## Usage

### Install

```
$ npm install reload-wrapper
```

#### Web page setting

You need include `/reload/reload.js` to your html.
(reload-wrapper not append your html)

```html
<script src="/reload/reload.js"></script>
```

or

```js
var reload = document.createElement("script");
reload.src = "/reload/reload.js";
document.body.appendChild(reload);
```


### Command Line

```
Usage: reload-wrapper [options]

Options:

  -V, --version                    output the version number
  -d, --dir [dir]                  The directory to serve up. Defaults to current dir. (default: /apps/getto/elm/tools)
  -w, --watch-dir [watch-dir]      The directory to watch. Defaults the serving directory.
  -e, --exts [extensions]          Extensions separated by commas or pipes. Defaults to html,js,css. (default: html|js|css)
  -p, --port [port]                The port to bind to. Can be set with PORT env variable as well. Defaults to 8080 (default: 8080)
  -v, --verbose [verbose]          Turning on logging on the server and client side. Defaults to false (default: false)
      --reload-js [reload-js]      The script to reload browser when contents changed. Defaults to /reload/reload.js (default: /reload/reload.js)
      --header-file [header-file]  Optional http headers for serving contents. Defaults to headers.json (default: headers.json)
  -h, --help                       output usage information
```


<a id="License"></a>
## License

reload-wrapper is licensed under the [MIT](LICENSE) license.

Copyright &copy; since 2018 shun@getto.systems
