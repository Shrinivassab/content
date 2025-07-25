---
title: tabs.getCurrent()
slug: Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent
page-type: webextension-api-function
browser-compat: webextensions.api.tabs.getCurrent
sidebar: addonsidebar
---

Get a {{WebExtAPIRef("tabs.Tab")}} containing information about the tab that this script is running in.

> [!NOTE]
> This function is only useful in contexts where there is a browser tab, such as an [options page](/en-US/docs/Mozilla/Add-ons/WebExtensions/Anatomy_of_a_WebExtension#sidebars_popups_and_options_pages).
>
> If you call it from a background script or a popup, it will return `undefined`.

This is an asynchronous function that returns a {{jsxref("Promise")}}.

## Syntax

```js-nolint
const gettingCurrent = browser.tabs.getCurrent()
```

### Parameters

None.

### Return value

A {{jsxref("Promise")}} that will be fulfilled with a {{WebExtAPIRef('tabs.Tab')}} object containing information about the current tab. If any error occurs the promise will be rejected with an error message.

## Examples

Get information about the current tab:

```js
function onGot(tabInfo) {
  console.log(tabInfo);
}

function onError(error) {
  console.log(`Error: ${error}`);
}

const gettingCurrent = browser.tabs.getCurrent();
gettingCurrent.then(onGot, onError);
```

{{WebExtExamples}}

## Browser compatibility

{{Compat}}

> [!NOTE]
> This API is based on Chromium's [`chrome.tabs`](https://developer.chrome.com/docs/extensions/reference/api/tabs#method-getCurrent) API. This documentation is derived from [`tabs.json`](https://chromium.googlesource.com/chromium/src/+/master/chrome/common/extensions/api/tabs.json) in the Chromium code.

<!--
// Copyright 2015 The Chromium Authors. All rights reserved.
//
// Redistribution and use in source and binary forms, with or without
// modification, are permitted provided that the following conditions are
// met:
//
//    * Redistributions of source code must retain the above copyright
// notice, this list of conditions and the following disclaimer.
//    * Redistributions in binary form must reproduce the above
// copyright notice, this list of conditions and the following disclaimer
// in the documentation and/or other materials provided with the
// distribution.
//    * Neither the name of Google Inc. nor the names of its
// contributors may be used to endorse or promote products derived from
// this software without specific prior written permission.
//
// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
-->
