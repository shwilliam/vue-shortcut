# vue-shortcut

> A declarative Vue wrapper for [jkup's shortcut library](https://github.com/jkup/shortcut). This component exposes methods that, when used, bind event listeners to common keyboard shortcuts.

[![vue-shortcut demo](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/qvj2vk6w79)

## Shortcuts

  Shortcut | Event Name
  ---------|-----------
      j    |   nextItem
      k    |   prevItem
      n    |   newItem
      o    |   openItem
      /    |   searchItems
      .    |   loadItems
      ?    |   showHelp

## Installation

Install the package from npm by running

```
$ npm install --save vue-shortcut
```

or

```
$ yarn add vue-shortcut
```

## Usage

Import, register and place the component in your Vue app. Attach a function to react to any of the events listed [above](##shortcuts) for example 'v-on:nextItem="doSomething"' or '@nextItem="doSomething"'.

```html
<template>
  <VueShortcut @nextItem="goForward" @prevItem="goBack" />
</template>

<script>
import VueShortcut from 'vue-shortcut';

export default {
  components: {
    VueShortcut
  }
}
</script>
```

## Dev

Running dev and example scripts require @vue/cli and @vue/cli-service-global to be installed.
Install globally by running

```
$ npm install --save --g @vue/cli @vue/cli-service-global
```

or

```
$ yarn add global vue/cli @vue/cli-service-global
```

## Contributing

This project is open to and encourages contributions! Feel free to discuss any bug fixes/features in the [issues](https://github.com/shwilliam/vue-shortcut/issues). If you wish to work on this project:

1.  [Fork the project](https://github.com/shwilliam/vue-shortcut/archive/master.zip)
2.  Create your feature branch (`git checkout -b new-feature-branch`)
3.  Commit your changes (`git commit -am 'add new feature'`)
4.  Push to the branch (`git push origin new-feature-branch`)
5.  [Submit a pull request!](https://github.com/shwilliam/vue-shortcut/pull/new/master)
