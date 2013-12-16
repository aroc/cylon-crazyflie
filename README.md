# Cylon.js For Crazyflie

Cylon.js (http://cylonjs.com) is a JavaScript framework for robotics and physical computing using Node.js

This module provides an adaptor and drivers for the Crazyflie nanocopter (http://www.bitcraze.se/). It uses the Aerogel node module (https://github.com/ceejbot/aerogel) created by [@ceejbot](https://github.com/ceejbot) thank you!

Want to use Ruby on robots? Check out our sister project Artoo (http://artoo.io)

Want to use the Go programming language to power your robots? Check out our sister project Gobot (http://gobot.io).

[![Build Status](https://secure.travis-ci.org/hybridgroup/cylon-crazyflie.png?branch=master)](http://travis-ci.org/hybridgroup/cylon-crazyflie)

## Getting Started

Install the module with: `npm install cylon-crazyflie`

You will also need to install the latest beta of firmware to the Crazyflie itself to use the 'hover' mode from [https://bitbucket.org/bitcraze/crazyflie-firmware/downloads/Crazyflie_2013.11-beta1.bin](https://bitbucket.org/bitcraze/crazyflie-firmware/downloads/Crazyflie_2013.11-beta1.bin)

## Examples

### JavaScript
```javascript
var Cylon = require('cylon');

Cylon.robot({
  connection: { name: 'crazyflie', adaptor: 'crazyflie', port: 'radio://1/10/250KPS' },
  device: {name: 'drone', driver: 'crazyflie'},

  work: function(my) {
    my.drone.on('start', function() {
      my.drone.takeoff();
      after((10).seconds(), function() { 
        my.drone.land();
      });
      after((15).seconds(), function() { 
        my.drone.stop();
      });
    });
  }
}).start();
```

### CoffeeScript
```
Cylon = require 'cylon'

Cylon.robot
  connection:
    name: 'crazyflie', adaptor: 'crazyflie', port: "radio://1/10/250KPS"

  device:
    name: 'drone', driver: 'crazyflie'

  work: (my) ->
    my.drone.on 'start', ->
      my.drone.takeoff()
      after 10.seconds(), ->
        my.drone.land()
      after 15.seconds(), ->
        my.drone.stop()

.start()
```

## Hover Mode

```
  my.drone.setParam('flightmode.althold', true);
```

## Documentation
We're busy adding documentation to our web site at http://cylonjs.com/ please check there as we continue to work on Cylon.js

Thank you!

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History

[![NPM](https://nodei.co/npm/cylon-crazyflie.png?compact=true)](https://nodei.co/npm/cylon-crazyflie/)

Version 0.2.0 - Release for cylon 0.8.0

Version 0.1.0 - Initial release

## License
Copyright (c) 2013 The Hybrid Group. Licensed under the Apache 2.0 license.
