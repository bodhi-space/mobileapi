## Kernel Events

The Kernel support handling events from native application.  
Developer can [add](#addeventlistener) or
[remove](#removeeventlistener) listener callbacks for the event.  
Events usually used module_name.module_event scheme for naming.

### Tasks

  * `addEventListener` function
  * `removeEventListener` function

### Functions

#### addEventListener

```javascript
events.addEventListener("module_name.module_event", function (eventInfo) {  
    alert("Received event with info: " + eventInfo);  
});
```

`events.addEventListener( eventName, callback )`

##### Discussion

Register `callback` for `eventName`

##### Arguments

  * `eventName` required

Event name. Usually used scheme module_name.module_event. For example
device.pause

  * `callback` required

Callback. Function which will be called when kernel receive event from
application.

##### Return Value

  * `this`

#### removeEventListener

```javascript
events.removeEventListener("module_name.module_event");
```

`events.removeEventListener( eventName, callback )`

##### Discussion

Unregister `callback` for `eventName`

##### Arguments

  * `eventName` required

Event name. Usually used scheme module_name.module_event. For example
device.pause

  * `callback` optional

Callback. Function which will be called when kernel receive event from application.

If not selected or `null` will be removed all callbacks for specified event

##### Return Value

  * `this`