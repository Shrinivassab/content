---
title: "<i>: The Idiomatic Text element"
slug: Web/HTML/Reference/Elements/i
page-type: html-element
browser-compat: html.elements.i
sidebar: htmlsidebar
---

The **`<i>`** [HTML](/en-US/docs/Web/HTML) element represents a range of text that is set off from the normal text for some reason, such as idiomatic text, technical terms, taxonomical designations, among others. Historically, these have been presented using italicized type, which is the original source of the `<i>` naming of this element.

{{InteractiveExample("HTML Demo: &lt;i&gt;", "tabbed-shorter")}}

```html interactive-example
<p>I looked at it and thought <i>This can't be real!</i></p>

<p>
  <i>Musa</i> is one of two or three genera in the family <i>Musaceae</i>; it
  includes bananas and plantains.
</p>

<p>
  The term <i>bandwidth</i> describes the measure of how much information can
  pass through a data connection in a given amount of time.
</p>
```

```css interactive-example
i {
  /* Add your styles here */
}
```

## Attributes

This element only includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

## Usage notes

- Use the `<i>` element for text that is set off from the normal prose for readability reasons. This would be a range of text with different semantic meaning than the surrounding text. Among the use cases for the `<i>` element are spans of text representing a different quality or mode of text, such as:
  - Alternative voice or mood
  - Taxonomic designations (such as the genus and species "_Homo sapiens_")
  - Idiomatic terms from another language (such as "_et cetera_"); these should include the [`lang`](/en-US/docs/Web/HTML/Reference/Global_attributes/lang) attribute to identify the language
  - Technical terms
  - Transliterations
  - Thoughts (such as "She wondered, _What is this writer talking about, anyway?_")
  - Ship or vessel names in Western writing systems (such as "They searched the docks for the _Empress of the Galaxy_, the ship to which they were assigned.")

- In earlier versions of the HTML specification, the `<i>` element was merely a presentational element used to display text in italics, much like the `<b>` element was used to display text in bold letters. This is no longer true, as these tags now define semantics rather than typographic appearance. A browser will typically still display the contents of the `<i>` element in italic type, but is, by definition, no longer required to do so. To display text in italic type, authors should use the CSS {{cssxref("font-style")}} property.
- Be sure the text in question is not actually more appropriately marked up with another element.
  - Use {{HTMLElement("em")}} to indicate stress emphasis.
  - Use {{HTMLElement("strong")}} to indicate importance, seriousness, or urgency.
  - Use {{HTMLElement("mark")}} to indicate relevance.
  - Use {{HTMLElement("cite")}} to mark up the name of a work, such as a book, play, or song.
  - Use {{HTMLElement("dfn")}} to mark up the defining instance of a term.

## Examples

This example demonstrates using the `<i>` element to mark text that is in another language.

```html
<p>
  The Latin phrase <i lang="la">Veni, vidi, vici</i> is often mentioned in
  music, art, and literature.
</p>
```

### Result

{{EmbedLiveSample("Examples")}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories"
          >Content categories</a
        >
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >Flow content</a
        >,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >, palpable content.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >Phrasing content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>None, both the starting and ending tag are mandatory.</td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>
        Any element that accepts
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <code
          ><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/generic_role"
            >generic</a
          ></code
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{HTMLElement("em")}}
- Other italicized elements: {{HTMLElement("var")}}, {{HTMLElement("dfn")}}, {{HTMLElement("cite")}}, {{HTMLElement("address")}}
