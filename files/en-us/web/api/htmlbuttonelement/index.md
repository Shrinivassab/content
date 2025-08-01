---
title: HTMLButtonElement
slug: Web/API/HTMLButtonElement
page-type: web-api-interface
browser-compat: api.HTMLButtonElement
---

{{APIRef("HTML DOM")}}

The **`HTMLButtonElement`** interface provides properties and methods (beyond the regular {{domxref("HTMLElement")}} interface it also has available to it by inheritance) for manipulating {{HTMLElement("button")}} elements.

{{InheritanceDiagram}}

## Instance properties

_Inherits properties from its parent, {{domxref("HTMLElement")}}._

- {{domxref("HTMLButtonElement.command")}}
  - : A string value indicating the action to be performed on an element being controlled by this button.
- {{domxref("HTMLButtonElement.commandForElement")}}
  - : A reference to an existing {{domxref("Element")}} that the button controls.
- {{domxref("HTMLButtonElement.disabled")}}
  - : A boolean value indicating whether or not the control is disabled, meaning that it does not accept any clicks.
- {{domxref("HTMLButtonElement.form")}} {{ReadOnlyInline}}
  - : An {{domxref("HTMLFormElement")}} reflecting the form that this button is associated with. If the button is a descendant of a form element, then this attribute is a reference to that form's associated `HTMLFormElement`.
    If the button is not a descendant of a form element, then the attribute can be a reference to any `HTMLFormElement` element in the same document it is related to, or the `null` value if none matches.
- {{domxref("HTMLButtonElement.formAction")}}
  - : A string reflecting the URI of a resource that processes information submitted by the button. If specified, this attribute overrides the [`action`](/en-US/docs/Web/HTML/Reference/Elements/form#action) attribute of the {{HTMLElement("form")}} element that owns this element.
- {{domxref("HTMLButtonElement.formEnctype")}}
  - : A string reflecting the type of content that is used to submit the form to the server. If specified, this attribute overrides the [`enctype`](/en-US/docs/Web/HTML/Reference/Elements/form#enctype) attribute of the {{HTMLElement("form")}} element that owns this element.
- {{domxref("HTMLButtonElement.formMethod")}}
  - : A string reflecting the HTTP method that the browser uses to submit the form. If specified, this attribute overrides the [`method`](/en-US/docs/Web/HTML/Reference/Elements/form#method) attribute of the {{HTMLElement("form")}} element that owns this element.
- {{domxref("HTMLButtonElement.formNoValidate")}}
  - : A boolean value indicating that the form is not to be validated when it is submitted. If specified, this attribute overrides the [`novalidate`](/en-US/docs/Web/HTML/Reference/Elements/form#novalidate) attribute of the {{HTMLElement("form")}} element that owns this element.
- {{domxref("HTMLButtonElement.formTarget")}}
  - : A string reflecting a name or keyword indicating where to display the response received after submitting the form. If specified, this attribute overrides the [`target`](/en-US/docs/Web/HTML/Reference/Elements/form#target) attribute of the {{HTMLElement("form")}} element that owns this element.
- {{domxref("HTMLButtonElement.labels")}} {{ReadOnlyInline}}
  - : A {{domxref("NodeList")}} that represents a list of {{HTMLElement("label")}} elements that are labels for this button.
- {{domxref("HTMLButtonElement.name")}}
  - : A string representing the object's name when submitted with a form. If specified, it must not be the empty string.
- {{domxref("HTMLButtonElement.popoverTargetAction")}}
  - : Gets and sets the action to be performed (`"hide"`, `"show"`, or `"toggle"`) on a popover element being controlled by a control button. It reflects the value of the [`popovertargetaction`](/en-US/docs/Web/HTML/Reference/Elements/button#popovertargetaction) HTML attribute.
- {{domxref("HTMLButtonElement.popoverTargetElement")}}
  - : Gets and sets the popover element to control via a button. The JavaScript equivalent of the [`popovertarget`](/en-US/docs/Web/HTML/Reference/Elements/button#popovertarget) HTML attribute.
- {{domxref("HTMLButtonElement.type")}}
  - : A string indicating the behavior of the button. This is an enumerated attribute with the following possible values:
    - `submit`: The button submits the form. This is the default value if the attribute is not specified, or if it is dynamically changed to an empty or invalid value.
    - `reset`: The button resets the form.
    - `button`: The button does nothing.
    - `menu`: The button displays a menu. {{experimental_inline}}

- {{domxref("HTMLButtonElement.willValidate")}} {{ReadOnlyInline}}
  - : A boolean value indicating whether the button is a candidate for constraint validation. It is `false` if any conditions bar it from constraint validation, including: its `type` property is `reset` or `button`; it has a {{HTMLElement("datalist")}} ancestor; or the `disabled` property is set to `true`.
- {{domxref("HTMLButtonElement.validationMessage")}} {{ReadOnlyInline}}
  - : A string representing the localized message that describes the validation constraints that the control does not satisfy (if any). This attribute is the empty string if the control is not a candidate for constraint validation (`willValidate` is `false`), or it satisfies its constraints.
- {{domxref("HTMLButtonElement.validity")}} {{ReadOnlyInline}}
  - : A {{domxref("ValidityState")}} representing the validity states that this button is in.
- {{domxref("HTMLButtonElement.value")}}
  - : A string representing the current form control value of the button.

## Instance methods

_Inherits methods from its parent, {{domxref("HTMLElement")}}_.

- {{domxref("HTMLButtonElement.checkValidity()")}}
  - : Returns `true` if the element's value has no validity problems; otherwise, returns `false`.
- {{domxref("HTMLButtonElement.reportValidity()")}}
  - : Performs the same action as `checkValidity()`, but also reports the result to the user if the `invalid` event was not canceled.
- {{domxref("HTMLButtonElement.setCustomValidity()")}}
  - : Sets the custom validity message for the element. Use the empty string to indicate that the element does _not_ have a custom validity error.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- HTML element implementing this interface: {{HTMLElement("button")}}
