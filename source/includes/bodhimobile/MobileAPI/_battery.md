## Battery Module

Getting information about battery level and plugged for charger state.

### Tasks

  * `level` property
  * `isPlugged` property
  * `levelChanged` function
  * `pluggedChanged` function
  * `low` function
  * `critical` function
  * `battery.level` event
  * `battery.plugged` event
  * `battery.low` event
  * `battery.critical` event

### Properties

#### level

```javascript
var level = battery.level;
```

##### Discussion

Current battery level.

<aside class="notice">
On iOS devices with os version < 8.0 battery level divisible by 5
</aside>

#### isPlugged

```javascript
var plugged = battery.isPlugged;
```

##### Discussion

Is device plugged for charger

### Functions

#### levelChanged

```javascript
battery.levelChanged( function(info) {  
    alert("Battery level changed. Current level: " + info.level);  
});
```

`battery.levelChanged( callback )`

##### Discussion

Register `callback` as observer for [`battery.level`](#battery.level) event.

##### Arguments

  * `callback` required

##### Return Value

  * `this`

#### pluggedChanged

```javascript
battery.pluggedChanged( function(info) {  
    alert(info.isPlugged ? "Device plugged" : "Device unplugged");  
});
```

`battery.pluggedChanged( callback )`

##### Discussion

Register `callback` as observer for [`battery.plugged`](#battery.plugged) event.

##### Arguments

  * `callback` required

##### Return Value

  * `this`  

#### low

```javascript
battery.low( function() {  
    alert("Battery low!");  
});
```

`battery.low( callback )`

##### Discussion

Register `callback` as observer for [`battery.low`](#battery.low) event.

##### Arguments

  * `callback` required

##### Return Value

  * `this`  

#### critical

```javascript
battery.critical( function() {  
    alert("Battery critical low!");  
});
```

`battery.critical( callback )`

##### Discussion

Register `callback` as observer for [`battery.critical`](#battery.critical) event.

##### Arguments

  * `callback` required

##### Return Value

  * `this`

### Events

#### `battery.level`

##### Discussion

Event received when changed battery level

#### `battery.plugged`

##### Discussion

Event received when device plugged or unplugged from charger

#### `battery.low`

##### Discussion

Event received when device unplugged from charger and battery level less then
20%

#### `battery.critical`

##### Discussion

Event received when device unplugged from charger and battery level less then
5%