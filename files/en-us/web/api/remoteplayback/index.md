---
title: RemotePlayback
slug: Web/API/RemotePlayback
page-type: web-api-interface
browser-compat: api.RemotePlayback
---

{{APIRef("Remote Playback API")}}

The **`RemotePlayback`** interface of the {{domxref('Remote Playback API','','',' ')}} allows the page to detect availability of remote playback devices, then connect to and control playing on these devices.

{{InheritanceDiagram}}

## Instance properties

_Also inherits properties from its parent interface, {{DOMxRef("EventTarget")}}._

- {{domxref("RemotePlayback.state")}} {{ReadOnlyInline}}
  - : Represents the `RemotePlayback` connection's state. One of:
    - `"connecting"`
      - : The user agent is attempting to initiate remote playback with the selected device.
    - `"connected"`
      - : The transition from local to remote playback has happened, all commands will now take place on the remote device.
    - `"disconnected"`
      - : The remote playback has not been initiated, has failed to initiate, or has been stopped.

## Instance methods

_Also inherits methods from its parent interface, {{DOMxRef("EventTarget")}}._

- {{domxref("RemotePlayback.watchAvailability()")}}
  - : Watches the list of available remote playback devices and returns a {{jsxref("Promise")}} that resolves with a `callbackId` of an available remote playback device.
- {{domxref("RemotePlayback.cancelWatchAvailability()")}}
  - : Cancels the request to monitor the availability of remote playback devices.
- {{domxref("RemotePlayback.prompt()")}}
  - : Prompts the user to select and give permission to connect to a remote playback device.

## Events

_Also inherits events from its parent interface, {{DOMxRef("EventTarget")}}._

- {{domxref("RemotePlayback.connecting_event", "connecting")}}
  - : Fired when the user agent initiates remote playback.
- {{domxref("RemotePlayback.connect_event", "connect")}}
  - : Fired when the user agent successfully connects to the remote device.
- {{domxref("RemotePlayback.disconnect_event", "disconnect")}}
  - : Fired when the user agent disconnects from the remote device.

## Examples

The following example demonstrates a player with custom controls that support remote playback. Initially the button used to select a device is hidden:

```html
<video id="videoElement" src="https://example.org/media.ext">
  <button id="deviceBtn" class="hidden">Pick device</button>
</video>
```

```css
.hidden {
  display: none;
}
```

The {{domxref("RemotePlayback.watchAvailability()")}} method is used to watch for available remote playback devices. If a device is available, use the callback to show the button.

```js
const deviceBtn = document.getElementById("deviceBtn");
const videoElem = document.getElementById("videoElement");

function availabilityCallback(available) {
  // Show or hide the device picker button depending on device availability.
  if (available) {
    deviceBtn.classList.remove("hidden");
  } else {
    deviceBtn.classList.add("hidden");
  }
}

videoElem.remote.watchAvailability(availabilityCallback).catch(() => {
  // If the device cannot continuously watch available,
  // show the button to allow the user to try to prompt for a connection.
  deviceBtn.classList.remove("hidden");
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
