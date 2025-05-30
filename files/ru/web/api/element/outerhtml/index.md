---
title: Element.outerHTML
slug: Web/API/Element/outerHTML
---

{{APIRef("DOM")}}

## Описание

Атрибут `outerHTML` DOM-интерфейса {{ domxref("element") }} получает сериализованный HTML-фрагмент, описывающий элемент, включая его потомков. Можно установить замену элемента узлами, полученными из заданной строки.

## Синтаксис

```
var content = element.outerHTML;
```

На выводе, `content` содержит сериализованный HTML-фрагмент, описывающий `element` и его потомки.

```
element.outerHTML = content;
```

Replaces the `element` with the nodes generated by parsing the string `content` with the parent of `element` as the context node for the fragment parsing algorithm.

## Примеры

Получение свойства `outerHTML` элемента:

```js
// HTML:
// <div id="d"><p>Content</p><p>Further Elaborated</p></div>

d = document.getElementById("d");
console.log(d.outerHTML);

// строка '<div id="d"><p>Content</p><p>Further Elaborated</p></div>'
// выведена в окно консоли
```

Замена ветки с помощью изменения свойства `outerHTML`:

```js
// HTML:
// <div id="container"><div id="d">Это div.</div></div>

container = document.getElementById("container");
d = document.getElementById("d");
console.log(container.firstChild.nodeName); // логирует "DIV"

d.outerHTML = "<p>Этот параграф заменил исходный div.</p>";
console.log(container.firstChild.nodeName); // логирует "P"

// div #d больше не часть дерева документа,
// новый параграф заменил его.
```

## Примечания

Если у элемента нет родительской ветки, которая не является корневой веткой документа, установка его свойства `outerHTML` выбросит исключение [`DOMException`](/en-US/DOM/DOMException) с кодом ошибки `NO_MODIFICATION_ALLOWED_ERR`. Например:

```js
document.documentElement.outerHTML = "test"; // бросает DOMException
```

Обратите внимание, когда произойдёт изменение элемента в документе, переменная, у которой было установлено свойство `outerHTML`, будет по-прежнему хранить ссылку на оригинальный элемент:

```js
var p = document.getElementsByTagName("p")[0];
console.log(p.nodeName); // показывает: "P"
p.outerHTML = "<div>Этот div заменил параграф.</div>";
console.log(p.nodeName); // всё ещё "P";
```

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- MSDN: [outerHTML Property](http://msdn.microsoft.com/en-us/library/ms534310%28v=vs.85%29.aspx)
