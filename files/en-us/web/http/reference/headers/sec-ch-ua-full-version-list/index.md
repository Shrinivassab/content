---
title: Sec-CH-UA-Full-Version-List header
short-title: Sec-CH-UA-Full-Version-List
slug: Web/HTTP/Reference/Headers/Sec-CH-UA-Full-Version-List
page-type: http-header
status:
  - experimental
browser-compat: http.headers.Sec-CH-UA-Full-Version-List
sidebar: http
---

{{SeeCompatTable}}{{SecureContext_Header}}

The HTTP **`Sec-CH-UA-Full-Version-List`** {{Glossary("request header")}} is a [user agent client hint](/en-US/docs/Web/HTTP/Guides/Client_hints#user_agent_client_hints) which provides the user-agent's branding and full version information.

The **`Sec-CH-UA-Full-Version-List`** header provides the brand and full version information for each brand associated with the browser, in a comma-separated list.

The header may include "fake" brands in any position and with any name.
This is a feature designed to prevent servers from rejecting unknown user agents outright, forcing user agents to lie about their brand identity.

> [!NOTE]
> This is similar to {{HTTPHeader("Sec-CH-UA")}}, but includes the full version number instead of the significant version number for each brand.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Header type</th>
      <td>
        {{Glossary("Request header")}},
        <a href="/en-US/docs/Web/HTTP/Guides/Client_hints">Client hint</a>
      </td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Forbidden request header")}}</th>
      <td>Yes (<code>Sec-</code> prefix)</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Sec-CH-UA-Full-Version-List: "<brand>";v="<full version>", …
```

The value is a comma separated list of brands in the user agent brand list, and their associated full version number.

### Directives

- `<brand>`
  - : A brand associated with the user agent, like "Chromium", "Google Chrome".
    This may be an intentionally incorrect brand like `" Not A;Brand"` or `"(Not(A:Brand"` (the actual value is expected change over time and be unpredictable).
- `<full version>`
  - : A full version number, such as 98.0.4750.0.

## Description

A brand is a commercial name for the user agent like: Chromium, Opera, Google Chrome, Microsoft Edge, Firefox, and Safari.
A user agent might have several associated brands.
For example, Opera, Chrome, and Edge are all based on Chromium, and will provide both brands in the `Sec-CH-UA-Full-Version-List` header.

The header allows the server to customize its response based on both shared brands and on particular customizations in their specific respective builds.

## Examples

### Using Sec-CH-UA-Full-Version-List

A server requests the `Sec-CH-UA-Full-Version-List` header by including the {{HTTPHeader("Accept-CH")}} in a _response_ to any request from the client, using the name of the desired header as a token:

```http
HTTP/1.1 200 OK
Accept-CH: Sec-CH-UA-Full-Version-List
```

The client may choose to provide the hint, and add the `Sec-CH-UA-Full-Version-List` header to subsequent requests, as shown below:

```http
GET /my/page HTTP/1.1
Host: example.site

Sec-CH-UA: " Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"
Sec-CH-UA-Mobile: ?0
Sec-CH-UA-Full-Version-List: " Not A;Brand";v="99.0.0.0", "Chromium";v="98.0.4750.0", "Google Chrome";v="98.0.4750.0"
Sec-CH-UA-Platform: "Linux"
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Client hints](/en-US/docs/Web/HTTP/Guides/Client_hints)
- [User-Agent Client Hints API](/en-US/docs/Web/API/User-Agent_Client_Hints_API)
- {{HTTPHeader("Accept-CH")}}
- [HTTP Caching: Vary](/en-US/docs/Web/HTTP/Guides/Caching#vary) and {{HTTPHeader("Vary")}} header
- [Improving user privacy and developer experience with User-Agent Client Hints](https://developer.chrome.com/docs/privacy-security/user-agent-client-hints) (developer.chrome.com)
