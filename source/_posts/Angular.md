---
title: Angular Note
date: 2020-09-19 12:32:39
tags:
  - Angular
categories:
  - 笔记
---

## 模板语法
```html
<div [class.special]="isSpecial">Special</div>
<button [style.color]="isSpecial ? 'red' : 'green'">
<button [attr.aria-label]="help">help</button>
<img bind-src="itemImageUrl"> = <img [src]="itemImageUrl">
```

尽管目标名称通常是 Property 的名称，但是在 Angular 中，有几个常见属性会自动将 Attribute 映射为 Property。这些包括 class / className，innerHtml / innerHTML 和 tabindex / tabIndex。

NgStyle 指令可以作为 [style] 绑定的替代指令。但是，应该把上面这种 [style] 样式绑定语法作为首选，因为随着 Angular 中样式绑定的改进，NgStyle 将不再提供重要的价值，并最终在未来的某个版本中删除。

```html
<button on-click="onSave($event)">on-click Save</button> = <button (click)="onSave($event)">Save</button>

<input [value]="currentItem.name"
       (input)="currentItem.name=$event.target.value" >
without NgModel
```

<input ref-fax placeholder="fax number" /> = <input #fax placeholder="fax number" />

## 










