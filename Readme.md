*This repository is a mirror of the [component](http://component.io) module [manuelstofer/koboldmaki](http://github.com/manuelstofer/koboldmaki). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/manuelstofer-koboldmaki`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Koboldmaki

![Build status](https://api.travis-ci.org/manuelstofer/koboldmaki.png)

![image](resources/koboldmaki.jpg)

Views inspired by Backbone, built with components only.

## Installation

Koboldmaki can be installed with [component](https://github.com/component/component)

```
$ component install manuelstofer/koboldmaki
```

## Usage

It's very similar to Backbone views. One of the main differences
is that Koboldmaki views are event emitters. The way to instantiate views is different as well. 
Koboldmaki is not class based.

```Javascript
var View = require('koboldmaki');

var MakiAlert = View.extend({
    events: {
        'clicked a': 'hideInTree'
    },

    initialize: function () {
        // do something
    },

    hideInTree: function () {
        this.el.innerHTML = 'Go koboldmaki, hide in a tree before they catch you!';
    },

    render: function () {
        this.el.innerHTML = '<div><a>catch a koboldmaki</a></div>';
    }
});

var makiAlert = new MakiAlert();
document.body.appendChild(makiAlert.el);
```

Koboldmaki provides a $ method that can query for DOM inside the view's root node
using component/query. The $ method does not return any nodes that belong 
to a nested sub view.

