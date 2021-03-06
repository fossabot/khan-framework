# khan [![NPM version](https://badge.fury.io/js/khan.svg)](https://npmjs.org/package/khan) [![Build Status](https://travis-ci.org/github.com/khan.svg?branch=master)](https://travis-ci.org/github.com/khan)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FPaulaoDev%2Fkhan-framework.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FPaulaoDev%2Fkhan-framework?ref=badge_shield)

> Khan framework js

- Example aplication using Khan [Demo](https://codepen.io/PaulaoDev/pen/jYzeyP)

## Installation

```html
<!-- CDN -->
<script src="https://cdn.rawgit.com/PaulaoDev/khan-framework/master/vendor/build/khan.min.js"></script>
<!-- OR OUTHER CDN -->
<script src="https://rawgit.com/PaulaoDev/khan-framework/master/vendor/build/khan.min.js"></script>
<!-- OR STATIC FILE -->
<script src="vendor/build/khan.min.js"></script>
```

## Usage

```js
let khan = new $khan();
let Router = khan.Router();
let Controllers = khan.$controller;
```

## Exemple Router
- Simple but effective and fast system made with ecmascript 6

```Js
let khan = new $khan();
let Router = khan.Router();
let Controllers = khan.$controller;

// Using Middleware
khan.set('ola', 'nome');
khan.use(function(next){
	this.msg = 'Ola mundo!!';
	next();
});

// Use router in aplication
khan.use(Router);

Router.any('/', function(){
    document.body.innerHTML += `Test middleware ${this.msg}`;
});

khan.listen();

```

## Exemple $controller
- Simple exemple [demo](https://gist.github.com/PaulaoDev/19ab5160dd772ddc25f9feb09e247429)

```html
<div khan-controller="index">
   My name is {{ $nome }}
</div>
```

```Js
let khan = new $khan();
let Router = khan.Router();
let Controllers = khan.$controller;

Controllers('index', function($scope){
    this.nome = "PaulaoDev";
    this.render();
});
```

## License

MIT © [PaulaoDev](jskhanframework@gmail.com)


[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FPaulaoDev%2Fkhan-framework.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FPaulaoDev%2Fkhan-framework?ref=badge_large)