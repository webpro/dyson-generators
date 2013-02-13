# dyson-generators

Fake data generators, used by [dyson](http://github.com/webpro/dyson) and [dyson-image](http://github.com/webpro/dyson-image).

## Installation

Install dyson-generators locally by including it in `package.json` as a `devDependency`:

    "devDependencies": {
        "dyson-generators": "~0.1"
    }

## Examples

    var g = require('dyson-generators');

    g.id()              // 1 (consecutive calls return 2, 3, 4, ..)
    g.random(20)        // 13
    g.name()            // 'John', 'Olivia`
    g.address.city()    // 'Mexico City', 'Beijing'
    g.address.zipUS()   // '53142', '71238'
    g.address.zipNL()   // '4715 FW', '7551 VT'
    g.time.byQuarter()  // '14:45', '9:00'

The `g.image.base64()` method is a proxy to [http://dummyimage.com](http://dummyimage.com) by default:

    // Returns 'data:image/png;base64,iVBORw0KGgoAAAANSUh...'
    g.image.base64({width:200, height: 200});

    // See http://dummyimage.com for documentation
    g.image.base64({path:'/200x300&text=dummyimage.com+rocks!'});

    // Return base64 image string from a custom image service
    g.image.base64({
        host: 'http://lorempixel.com',
        path: '/150/150/abstract/' + g.random(10)
    });
