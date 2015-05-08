#### Screen Lock Module

This module provides the ability to work with native authentication.

Developer can get current activated authentication type and show UI for changing it.

Also he can lock his application and get authentication status after unlocking.

### Tasks

  * `TYPES` constant
  * `supported` property
  * `type` property
  * `setup` function
  * `lock` function
  * `screenLock.type` event

### Constants

##### TYPES

###### Discussion

This enum contains all variants of supported authentication types.

  * `screenLock.TYPES.NONE`

Native authentication deactivated.

  * `screenLock.TYPES.PIN`

Using PIN for unlock device or application.

  * `screenLock.TYPES.PATTERN`

Using Pattern (User should provide the path in 3x3 numbers grid) for unlock device or application.

  * `screenLock.TYPES.PASSWORD`

Using Password for unlock device or application.

  * `screenLock.TYPES.FINGERPRINT`

Using Fingerprint (TouchID for iOS) for unlock device or application.

### Properties

##### supported

###### Discussion

```javascript
var supported = screenLock.supported;
```

Returns whether the Mobile Container supports native authentication.

##### type

```javascript
var type = screenLock.type;
```

###### Discussion

Current native authentication type. See `TYPES` enum for variants.

### Functions

##### setup

```javascript
screenLock.setup( function(info) {  
    alert("Setup Finished");
}, function (error) {  
    alert("code: " + error.code + "\nmessage: " + error.message);  
});
```

`screenLock.setup( successCallback, errorCallback )`

###### Discussion

Shows the UI for changing current native authentication method or turning off it.

Developer can be notified of selected method with `type` property and `screenLock.type` event.

###### Arguments

  * `succesCallback` optional

Success callback. Called when function finished without errors

Callback parameter is always **null**

  * `errorCallback` optional

Error Callback. Called when function return error.

###### Return Value

  * [BodhiMobilePromise](#kernel-promise) object 

##### lock

```javascript
screenLock.lock( function(info) {
    if (info.unlocked)
      alert("Unlocked");
    else
      alert("Not unlocked");
}, function (error) {  
    alert("code: " + error.code + "\nmessage: " + error.message);  
});
```

`screenLock.lock( successCallback, errorCallback )`

###### Discussion

Locks the application.

###### Arguments

  * `succesCallback` optional

Success callback. Called when function finished without errors

Callback parameter is object which contains:

      * `unlocked` \- *true* if application was unlocked successfully. Otherwise *false*. (Boolean)

  * `errorCallback` optional

Error Callback. Called when function return error.

###### Return Value

  * [BodhiMobilePromise](#kernel-promise) object 

### Events

##### screenLock.type

```javascript
events.addEventListener("screenLock.type", function (info)
{
    var type = info.type;
});
```

###### Discussion

Event received when user changes native authentication type.

###### Callback Arguments

  * `type` \- The updated native authentication type. See `TYPES` enum for variants. (String)
