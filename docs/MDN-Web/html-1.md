
## 1 Main root

`<html>`

## 2 Document metadata

??? quote "元数据包含有关页面的信息。"

    这包括有关样式，脚本和数据的信息，以帮助软件（搜索引擎，浏览器等）使用和渲染页面。

    样式和脚本的元数据可以在页面中定义，也可以链接到具有该信息的另一个文件。 

`<base>`, `<head>`, `<link>`, `<meta>`, `<style>`, `<title>`


## 3 Sectioning root

`<body>`

??? note "`<body>`"

    onload: 文档加载完成后调用的函数。


## 4 Content sectioning

* `<article>`, `<aside>`, `<footer>`, `<header>`, `<main>`, `<section>`
* `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`

* `<nav>`, `<address>`, `<hgroup>`

## 5 Text content

* `<div>`, `<p>`, `<ol>`, `<ul>`, `<li>`, `<dl>`, `<dt>`, `<dd>`, `<pre>`, `<hr>`, `<blockquote>`

* `<figcaption>`, `<figure>`

## 6 Inline text semantics

* `<a>`, `<br>`, `<em>`, `<strong>`, `<code>`, `<q>`, `<span>`

* ...

## 7 Image and multimedia

* `<img>`

* ...

## 8 Embedded content

* `<iframe>`

* ...

## 9 Scripting

* `<canvas>`, `<noscript>`, `<script>`

## 10 Demarcating edits

> 这些元素使您可以标示出文本的特定部分已被更改。

* `<del>`, `<ins>`

## 11 Table content

* `<caption>`, `<colgroup>`, `<table>`, `<tbody>`, `<td>`, `<tfoot>`, `<th>`, `<thead>`, `<tr>`

* `<col>` 

## 12 Forms

* `<form>`, `<input>`
* `<label>`, `<button>`, `<select>`, `<option>`, `<textarea>`

* `<datalist>`, `<fieldset>`, `<legend>`, `<meter>`, `<optgroup>`, `<output>`, `<progress>`

## 13 Interactive elements

* `<details>`, `<dialog>`, `<menu>`, `<summary>`

## 14 Web Components

??? quote "Web 组件是与 HTML 相关的技术"

    从本质上讲，它可以像常规 HTML 一样创建和使用自定义元素。
    
    另外，您可以创建标准 HTML 元素的自定义版本。

* `<slot>`, `<template>`

??? note "<template\>"

    HTML 内容模板（<template\>）元素是一种用于保持(holding) HTML 的机制，该 HTML 在加载页面时不会立即渲染，但随后可以在运行时使用 JavaScript 实例化。

