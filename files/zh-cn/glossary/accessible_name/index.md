---
title: 无障碍名称
slug: Glossary/Accessible_name
l10n:
  sourceCommit: d9c3dac231bb6cbc138d761dbe0ad2f9a38b864f
---

{{GlossarySidebar}}

**无障碍名称**（Accessible Name）是一个用户界面元素的名字——一段文本，关联了一个可以通过一个与之相关的标签向用户提供协助技术 HTML 元素。

无障碍名称表达了这个元素的目的，帮助用户理解这个元素是干什么用的、怎么用的。一般来说，在一个页面之中，元素的无障碍名称应该是独一无二的。这可以帮助用户分辨元素、认出他们所希望与之交互的元素。

取决于元素以及 HTML 标记，无障碍名称的值可能会源于可见的内容（比如，在 {{HTMLElement("figcaption")}} 中的文字）或不可见的内容（比如，设置在一个元素上的 `aria-label` 属性），或者它们两个的组合。一个元素的无障碍名称的确定，取决于[无障碍名称计算](https://www.w3.org/WAI/ARIA/apg/practices/names-and-descriptions/#name_calculation)（这种计算对于不同元素是不同的）。

使用可见文本作为元素的无障碍名称，最好不过了。很多的元素，包括 {{HTMLElement("a")}}、{{HTMLElement("td")}} 还有 {{HTMLElement("button")}}，都能从它们的内容获取它们的无障碍名称。比如说，给定的 `<a href="foo.html">Bar</a>`，它所对应的无障碍名称就是“Bar”。

其他的元素从它们所关联的元素中获取无障碍名称。比如说，当一个 {{HTMLElement("fieldset")}} 或 {{HTMLElement("table")}} 元素分别包含一个子元素 {{HTMLElement("legend")}} 或 {{HTMLElement("caption")}}，这个嵌套元素的关系就会给父元素自动提供一个无障碍名称。对于表单元素，比如 {{HTMLElement("textarea")}}、{{HTMLElement("input")}}，它们的无障碍名称来源于与它们关联的 {{HTMLElement("label")}} 元素。这个关系需要通过将 `<label>` 元素的 `for` 属性与表单元素的 `id` 相匹配的方式来显式定义。又或者，一个显式的关系会在将表单元素直接嵌套在 `<label>` 元素之中的时候被创建。

对于某些元素，它们的无障碍名称来源于它们的属性，比如说 {{HTMLElement("img")}} 的 `alt` 属性。给定 `<img src="grape.jpg" alt="banana"/>`，它的无障碍名称就是“banana”。

要创建可见内容或多个文本节点与元素之间的关系，可以使用 [`aria-labeledby`](/zh-CN/docs/Web/Accessibility/ARIA/Attributes/aria-labelledby) 属性。如果没有将可见文本与一个需要无障碍名称的元素相关联，则可以使用 [`aria-label`](/zh-CN/docs/Web/Accessibility/ARIA/Attributes/aria-label) 属性。行级文本不应该拥有无障碍名称，比如 {{HTMLElement("code")}}、{{HTMLElement("del")}} 和 {{HTMLElement("mark")}}。

大多数的元素，比如一节文本内容，不需要无障碍名称。所有的控件都应该具有无障碍名称。所有传递了信息且不纯粹是展示性质的图片也应该这样。

辅助技术会给用户提供无障碍名称属性（也就是无障碍名称以及元素的角色）。虽然很多元素不需要无障碍名称，但是一些内容的[角色](/zh-CN/docs/Web/Accessibility/ARIA/Roles)可以从它们的无障碍名称中受益。比如说，[`tabpanel`](/zh-CN/docs/Web/Accessibility/ARIA/Roles/tabpanel_role) 是一块会在用户激活了与 [`tab`](/zh-CN/docs/Web/Accessibility/ARIA/Roles/tab_role) 角色相关联的元素之后展示出来的内容。可以将这个角色可以设置到不需要无障碍名称的元素上，例如 {{HTMLElement("div")}} 元素。`tabpanel` 是 `tab` 的后代（内容部分）。给 `tabpanel` 添加 `aria-labelledby` 是最佳实践。

## 参见

- [ARIA 角色](/zh-CN/docs/Web/Accessibility/ARIA/Roles)
- [ARIA 属性](/zh-CN/docs/Web/Accessibility/ARIA/Attributes)
- [无障碍](/zh-CN/docs/Web/Accessibility)
- [学习无障碍](/zh-CN/docs/Learn/Accessibility)
