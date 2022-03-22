# blockly-field-date [![Built on Blockly](https://tinyurl.com/built-on-blockly)](https://github.com/google/blockly)

A [Blockly](https://www.npmjs.com/package/blockly) advanced date picker field that uses the Google Closure date picker.

## About

Custom date formats using `token` option (e.g. `yyyy-LL-dd`)

![blockly-field-date](https://raw.githubusercontent.com/tomas-berg/blockly-field-date/main/docs/demo.png)

## Installation

### npm

```bash
npm install --save blockly-field-date
```

### yarn

```bash
yarn add blockly-field-date
```

## Build

```bash
yarn build
```

## Usage

### JavaScript

```js
import * as Blockly from 'blockly';
import FieldDate from 'blockly-field-date';

Blockly.Blocks['test_field_date'] = {
  init: function () {
    this.appendDummyInput()
      .appendField('date: ')
      .appendField(new FieldDate('2022-01-11'), 'FIELDNAME');
  }
};
```

### JSON

```js
import * as Blockly from 'blockly';
import 'blockly-field-date';

Blockly.defineBlocksWithJsonArray([
    {
        type: 'test_field_date',
        message0: 'date: %1',
        args0: [
            {
                type: 'field_date',
                name: 'FIELDNAME',
                date: '2022-01-11
            }
        ]
    }]);
```

### JavaScript - extended options

```js
Blockly.Blocks['test_field_date'] = {
  init: function () {
    this.appendDummyInput()
      .appendField('date: ')
      .appendField(new FieldDate('1/11/2022', null, true, 'L/d/yyyy'), 'FIELDNAME');
  }
};
```

### JSON - extended options

```js
Blockly.defineBlocksWithJsonArray([
    {
        type: 'test_field_date',
        message0: 'date: %1',
        args0: [
            {
                type: 'field_date',
                name: 'FIELDNAME',
                date: '1/11/2022',
                token: 'L/d/yyyy',
                textEdit: true
            }
        ]
    }]);
```

### Run in browser

*You need to build the package first.*

```js
<script src="./dist/date_compressed.js"></script>
```

## License

Apache 2.0
