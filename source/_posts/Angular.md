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

<input ref-fax placeholder="fax number" /> = <input #fax placeholder="fax number" />
```

要监视 @Input() 属性的更改，请使用 Angular 的生命周期钩子之一 OnChanges。OnChanges 是专门设计用于具有 @Input() 装饰器的属性的。欲知详情，请参见生命周期钩子指南的OnChanges部分。


```html
类型转换函数 $any()
有时候，绑定表达式可能会在 AOT 编译时报类型错误，并且它不能或很难指定类型。要消除这种报错，你可以使用 $any() 转换函数来把表达式转换成 any 类型，范例如下：

<p>The item's undeclared best by date is: {{$any(item).bestByDate}}</p>
当 Angular 编译器把模板转换成 TypeScript 代码时，$any 表达式可以防止 TypeScript 编译器在进行类型检查时报错说 bestByDate 不是 item 对象的成员。

$any() 转换函数可以和 this 联合使用，以便访问组件中未声明过的成员。

<p>The item's undeclared best by date is: {{$any(this).bestByDate}}</p>
$any() 转换函数可以用在绑定表达式中任何可以进行方法调用的地方。
```
可以将 SVG 用作 Angular 中的有效模板

## 用户输入

```html
<input #box (keyup)="0">
<p>{{box.value}}</p>

<input #box (keyup.enter)="onEnter(box.value)">
<p>{{value}}</p>
```

## NgModules

这些可声明的类在当前模块中是可见的，但是对其它模块中的组件是不可见的 —— 除非把它们从当前模块导出， 并让对方模块导入本模块。

每个可声明对象都只能属于一个模块，所以只能把它声明在一个 @NgModule 中。当你需要在其它模块中使用它时，就要在那里导入包含这个可声明对象的模块。

BrowserModule 的提供者是面向整个应用的，所以它只能在根模块中使用，而不是特性模块。




## Angular问题笔记
文档列表版本下拉选择出现不显示的bug，发现组件的versionSet如果一样就不更新，版本1.1设置成1.2不一样后就可以了


