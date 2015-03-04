## Device Module

Getting basic information about device.  
Also provides events about application state.

### Tasks

  * `device.TYPES` constant
  * `model` property
  * `platform` property
  * `guid` property
  * `osVersion` property
  * `name` property
  * `type` property
  * `ready` function
  * `pause` function
  * `resume` function
  * `device.pause` event
  * `device.resume` event

### Constants

#### device.TYPES

##### Discussion

The enum contains variants of device types.

  * `device.TYPES.PHONE`

	Device is a phone.

  * `device.TYPES.TABLET`

	Device is a tablet.

### Properties

#### model

```javascript
var deviceModel = device.model;
```

##### Discussion

Device model. For example iPhone6,1 or iPhone6,2 for iPhone 5s


#### platform

```javascript
var devicePlatform = device.platform;
```

##### Discussion

Device Platform. Supported values:

  * iOS
  * Android
  * WP

#### guid

```javascript
var deviceId = device.guid;
```

##### Discussion

Device identifier

#### osVersion

```javascript
var osVersion = device.osVersion;
```

##### Discussion

Device OS version

#### name

```javascript
var deviceName = device.name;
```

##### Discussion

Device Name

#### type

```javascript
var deviceType = device.type;
```

##### Discussion

Device Type. See device.TYPES for more info.

### Functions

#### ready

```javascript
device.ready( function() {  
    alert("Initializtion complete");  
});
```

`device.ready( callback )`

##### Discussion

Add _callback_ which will be called after full JavaScript kernel and modules
initialization.  
If call this function after initialization end _callback_ will be called
immediately.

##### Arguments

  * `callback` required

Callback which execute after JavaScript kernel initialization.

##### Return Value

  * `this`

#### pause

```javascript
device.pause( function() {  
    alert("Application will enter to background");  
});
```

`device.pause( callback )`

##### Discussion

Register _callback_ as observer for device.pause event.

##### Arguments

  * `callback` required

Callback which execute when application enter to background.

##### Return Value

  * `this`

#### resume

```javascript
device.resume( function() {  
    alert("Application will enter to foreground");  
});
```

`device.resume( callback )`

##### Discussion

Register _callback_ as observer for device.resume event.

##### Arguments

  * `callback` required

Callback which execute when application return to foreground.

##### Return Value

  * `this`

### Events

#### `device.pause`

##### Discussion

Event received when application enter to background

#### `device.resume`

##### Discussion

Event received when application returned from background

