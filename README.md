# @taktikorg/non-eius

[![Build and Test](https://github.com/taktikorg/non-eius/actions/workflows/node.js.yml/badge.svg)]()  [![NPM version](https://img.shields.io/npm/v/@taktikorg/non-eius.svg)](https://www.npmjs.com/package/@taktikorg/non-eius) ![NPM](https://img.shields.io/npm/l/@taktikorg/non-eius)

Minimal templates for Node.js

## Installation

```bash
npm install @taktikorg/non-eius
```

## Usage

```js
const compile = require('@taktikorg/non-eius');

const compiled = compile('filedir/filename.ct', { name: 'John' }); // filepath and variables
```

## Full example

```bash
├── root
│   ├── index.js
│   └── template.ct # template file you can use any extension
```
    
```js
// index.js
const compile = require('@taktikorg/non-eius');

const compiled = compile('template.ct', { name: 'John' }); // you can pass file content as third argument 
console.log(compiled); // you can also write to a file or do whatever you want with the compiled template
```

```html
<!-- template.ct -->
<h1>Hello, ${name}!</h1>
<h2>How are you? ${capitalize(name)}</h2>
<h3>Lowercase: ${lowercase(name)}</h3>
```

```html
<!-- output -->
<h1>Hello, John!</h1>
<h2>How are you? John</h2>
<h3>Lowercase: john</h3>
```

### Functions
- `capitalize(string)` - Capitalizes the first letter of a string
- `lowercase(string)` - Converts a string to lowercase
- `uppercase(string)` - Converts a string to uppercase
- `pluralize(string)` - Change the word to its plural
- `singularize(string)` - Change the word to its singular
- `capPluralize(string)` - capitalize + pluralize
- `capSingularize(string)` - capitalize + singularize
- `time()` - return timestamp


## Notes
- You can't provide whitespace in the function name, so `capitalize (name)` won't work. You can use `capitalize(name)` instead.
- `${ name}` won't work. You can use ${name} instead.
- You can use any extension for the template file, but it's recommended to use `.ct` for compile-template files.