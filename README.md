
# express-vue-engine [![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-image]][daviddm-url] [![Coverage percentage][coveralls-image]][coveralls-url]
> Vue rendering engine for Express.js

## Installation

```sh
$ npm install --save express-vue-engine
```

## Usage

```js
var expressVueEngine = require('express-vue-engine');

var app = express();
app.set('vue', {
    layoutsDir: 'app/components/',
    defaultLayout: 'layout'
});
app.engine('vue', expressVueEngine);
app.set('view engine', 'vue');
```

## Requirements

It requires you to have a file called layout.vue file similar to this in the `app/components/` directory

It's required to set the `{{{body}}}` and `{{{script}}}` tags where you want the layout body and script to go.

Finally you'll need to set the link to your copy of vue.js in the script... (this will become automatic soon)

```vue
<template>
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
            <title>{{title}}</title>
            <script src="assets/vue.js" charset="utf-8"></script>
        </head>
        <body>
            <div class="content">
                <div class="content-inner">
                    {{{body}}}
                </div>
            </div>
            {{{script}}}
        </body>
    </html>
</template>

<script>
export default {
    el: 'head',
    data () {
        return {
            title: 'dog'
        }
    },
    computed: {},
    ready () {},
    attached () {},
    methods: {},
    components: {}
}
</script>

<style>
</style>
```

## License

Apache-2.0 © [Daniel Cherubini](https://cherubini.casa)


[npm-image]: https://badge.fury.io/js/express-vue-engine.svg
[npm-url]: https://npmjs.org/package/express-vue-engine
[travis-image]: https://travis-ci.org/danmademe/express-vue-engine.svg?branch=master
[travis-url]: https://travis-ci.org/danmademe/express-vue-engine
[daviddm-image]: https://david-dm.org/danmademe/express-vue-engine.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/danmademe/express-vue-engine
[coveralls-image]: https://coveralls.io/repos/danmademe/express-vue-engine/badge.svg
[coveralls-url]: https://coveralls.io/r/danmademe/express-vue-engine
