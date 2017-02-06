# Angular wrapper for Select2 (ng2-select2)

[![npm version](https://badge.fury.io/js/ng2-select2.svg)](https://badge.fury.io/js/ng2-select2) [![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)

For Angular version 2.x.x and up


## Prerequisites

For this plugin to work you need to add two javascript libraries to your project
- [Jquery](https://jquery.com/download/)
- [Select2](https://select2.github.io/)

First option and **preferred one** is to add libraries to your package builder.
- You can find example of how to add libraries to the Angular CLI in [demo branch](https://github.com/NejcZdovc/ng2-select2/blob/demo/angular-cli.json#L24-L25). 
- You can also add it to [webpack directly](https://stackoverflow.com/questions/28969861/managing-jquery-plugin-dependency-in-webpack#answer-2898947). 

Second option is to include libraries into your html head:

```
<head>
  <meta charset="utf-8">
  <title>Ng2Select2Demo</title>
  <base href="/">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
  <script src="./assets/jquery.min.js"></script>		
  <script src="./assets/select2.min.js"></script>
</head>
```

## Installation

Add package to your project `npm i -S ng2-select2` (this will save package to your `dependencies` in `package.json`)


## Basic implementation

1) Add declaration to [NgModule](https://github.com/NejcZdovc/ng2-select2/blob/demo/src/app/app.module.ts#L15)
```
import { Select2Module } from 'ng2-select2';

@NgModule({
  imports: [
    ....,
    Select2Module
  ],
  ...
})
```

2) Add it to your [template](https://github.com/NejcZdovc/ng2-select2/blob/demo/src/app/app.component.html#L6). You need to define at least `data` `@Input`.

Example of `exampleData` can be found [here](https://github.com/NejcZdovc/ng2-select2/blob/demo/src/app/demos/basic/basic.component.ts#L13).

```
<select2 [data]="exampleData"></select2>
```


## Options

### Inputs
* **data** `Array<Select2OptionData`: Data used for generating select 2
* **value** `string`: Default value for select 2
* **cssImport** `boolean`: Disable or enable default style for select 2, default value is `true`
* **width** `string`: Set width for the input, default value is `resolve`
* **disabled** `boolean`: Disable select2, default value is `false`
* **options** `Select2Options`: Set options for select 2, [all available options](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/4869992bc079b88280b9ff91213528904109e8ae/select2/index.d.ts#L40) for select 2

### Outputs
* **valueChanged** `string`: Emitted when value changes in select 2 drop down 


## Demo

You can view a live demo [here](https://nejczdovc.github.io/ng2-select2/) or check out [demo branch](https://github.com/NejcZdovc/ng2-select2/tree/demo) where you can find source of this demo created with Angular CLI.

Every single demo is separate component. Bellow you can find links to components with descriptions.

#### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/basic)
- basic demo with only data input

#### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/options) with options
- width option
- theme option
- multiple option
- closeOnSelect option

#### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/template) with custom template demo
- custom template for drop down
- custom template for select2 input

#### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/change) with data changing demo
- when you change value in drop down, new value is displayed on the screen
- you can change selected value
- you can change select2 data

#### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/dynamic) with dynamic load demo
- data is loaded with 4 second delay
- selected value is loaded with 6 second delay

### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/matcher) with a custom matcher
- we only match results if they are the same from the start of the string

### [Demo](https://github.com/NejcZdovc/ng2-select2/tree/demo/src/app/demos/multiple) with a multiple options
- multiple options
- default value