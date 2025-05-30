---
title: "<figure>: Элемент иллюстрации с необязательной подписью"
slug: Web/HTML/Reference/Elements/figure
---

{{HTMLSidebar}}

**HTML-элемент `<figure>` (Иллюстрация с необязательной подписью)** представляет самостоятельный контент, часто с подписью (заголовком), которая указывается с помощью элемента ({{HTMLElement("figcaption")}}). Диаграмма и её подпись представляет собой единое целое.

{{InteractiveExample("HTML Demo: &lt;figure&gt;", "tabbed-shorter")}}

```html interactive-example
<figure>
  <img
    src="/shared-assets/images/examples/elephant.jpg"
    alt="Elephant at sunset" />
  <figcaption>An elephant at sunset</figcaption>
</figure>
```

```css interactive-example
figure {
  border: thin #c0c0c0 solid;
  display: flex;
  flex-flow: column;
  padding: 5px;
  max-width: 220px;
  margin: auto;
}

img {
  max-width: 220px;
  max-height: 150px;
}

figcaption {
  background-color: #222;
  color: #fff;
  font: italic smaller sans-serif;
  padding: 3px;
  text-align: center;
}
```

| [Категории контента](/ru/docs/Web/HTML/Guides/Content_categories) | [Основной поток](/ru/docs/Web/HTML/Guides/Content_categories#основной_поток), [секционный корень](/ru/docs/Web/HTML/Guides/Content_categories#прочие_модели_контента), явный контент                                                        |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Допустимое содержимое                                             | Элемент {{HTMLElement("figcaption")}} за которым следует [основной поток](/ru/docs/Web/HTML/Guides/Content_categories#основной_поток); или поточный контент за которым следует элемент {{HTMLElement("figcaption")}}; или поточный контент. |
| Пропуск тегов                                                     | Нет, открывающий и закрывающий теги обязательны.                                                                                                                                                                                            |
| Допустимые родители                                               | Любые элементы принимающие [основной поток](/ru/docs/Web/HTML/Guides/Content_categories#основной_поток).                                                                                                                                    |
| Допустимые ARIA-роли                                              | <code><a href="/ru/docs/Web/Accessibility/ARIA/Roles/group_role">group</a></code>, <code><a href="/ru/docs/Web/Accessibility/ARIA/Roles/presentation_role">presentation</a></code>                                                          |
| DOM-интерфейс                                                     | {{domxref("HTMLElement")}}                                                                                                                                                                                                                  |

## Атрибуты

Этот элемент поддерживает только [глобальные атрибуты](/ru/docs/Web/HTML/Reference/Global_attributes).

## Примечания по использованию

- Обычно `<figure>` это рисунок, иллюстрация, диаграмма, фрагмент кода, и т.д., на который ссылаются в основном потоке документа, но может быть перенесён в другую часть документа или в приложение не нарушив основной поток.
- Являясь [секционным корнем](/ru/docs/Web/HTML/Guides/Content_categories#прочие_модели_контента), структура содержимого элемента `<figure>` исключается из основной структуры документа.
- Подпись может быть связана с элементом `<figure>` с помощью вставки {{HTMLElement("figcaption")}} внутри него (как первый или последний потомок). Первый элемент `<figcaption>` в иллюстрации предоставляет её подпись (заголовок).

## Примеры

### Иллюстрации

```html
<!-- Just an image -->
<figure>
  <img
    src="/shared-assets/images/examples/favicon144.png"
    alt="The beautiful MDN logo." />
</figure>

<!-- Image with a caption -->
<figure>
  <img
    src="/shared-assets/images/examples/favicon144.png"
    alt="The beautiful MDN logo." />
  <figcaption>MDN Logo</figcaption>
</figure>
```

{{EmbedLiveSample("Иллюстрации", "100%", 375)}}

### Фрагменты кода

```html
<figure>
  <figcaption>Get browser details using <code>navigator</code>.</figcaption>
  <pre>
function NavigatorExample() {
  var txt;
  txt = "Browser CodeName: " + navigator.appCodeName + "; ";
  txt+= "Browser Name: " + navigator.appName + "; ";
  txt+= "Browser Version: " + navigator.appVersion  + "; ";
  txt+= "Cookies Enabled: " + navigator.cookieEnabled  + "; ";
  txt+= "Platform: " + navigator.platform  + "; ";
  txt+= "User-agent header: " + navigator.userAgent  + "; ";
  console.log("NavigatorExample", txt);
}
  </pre>
</figure>
```

{{EmbedLiveSample("Фрагменты_кода", "100%", 250)}}

### Цитирования

```html
<figure>
  <figcaption><cite>Edsger Dijkstra:</cite></figcaption>
  <blockquote>
    If debugging is the process of removing software bugs, then programming must
    be the process of putting them in.
  </blockquote>
</figure>
```

{{EmbedLiveSample("Цитирования")}}

> "Если отладка — процесс удаления ошибок, то программирование должно быть процессом их внесения", — Эдсгер Дейкстра.

### Стихи

```html
<figure>
  <p style="white-space:pre">
    Bid me discourse, I will enchant thine ear, Or like a fairy trip upon the
    green, Or, like a nymph, with long dishevell'd hair, Dance on the sands, and
    yet no footing seen: Love is a spirit all compact of fire, Not gross to
    sink, but light, and will aspire.
  </p>
  <figcaption><cite>Venus and Adonis</cite>, by William Shakespeare</figcaption>
</figure>
```

{{EmbedLiveSample("Стихи", "100%", 250)}}

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- Элемент {{HTMLElement("figcaption")}}.
