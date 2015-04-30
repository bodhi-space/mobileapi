#### Audio Module

This module allows playing and recording audio.

### Tasks

  * `AudioItemState` constant
  * `AudioItem` object
  * `getAudio` function

### Constants

##### AudioItemState

###### Discussion

This enum contains variants of [AudioItem](#audioitem-class) object states.

  * `AudioItemState.STOPPED`

Audio record currently stopped.

  * `AudioItemState.PLAYING`

Audio record currently playing.

  * `AudioItemState.PAUSED`

Audio record currently paused.

  * `AudioItemState.RECORDED`

Audio record currently recorded.

### Objects

##### AudioItem

###### Discussion

This object contains information about audio records and allows developer to record, play and control audio. See [AudioItem Class](#audioitem-class) to get more information.

### Functions

##### getAudio

```javascript
audio.getAudio( function(info) {  
    alert("AudioItem created: " + info.audioItem);
}, function (error) {  
    alert("code: " + error.code + "\nmessage: " + error.message);  
});
```

`audio.getAudio( options, successCallback, errorCallback )`

###### Discussion

Creates new [AudioItem](#audioitem-class) object which used for all audio operations.

###### Arguments

  * `options` optional

Object with key-value. Supported keys:

    * `key` optional

A String value. The key in [App Storage](#app-storage-module). If not specified, method will create a new automatically.

  * `succesCallback` optional

Success callback. Called when function finished without errors

Callback parameter is object which contains:

    * `audioItem` \- The created [AudioItem](#audioitem-class) object.

  * `errorCallback` optional

Error Callback. Called when function return error.

###### Return Value

  * [BodhiMobilePromise](#kernel-promise) object
