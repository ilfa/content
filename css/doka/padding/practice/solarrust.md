---
tags:
  - practice
permalink: false
---

🛠 Самая прикольная фишка, которую можно реализовать при помощи `padding` — адаптивные картинки, которые при изменении ширины экрана изменяют свой размер, но не деформируются.

```html
<!-- Элемент для трюка в padding -->
<div class="responsive image-box"></div>

<!-- Просто блок с фоновой картинкой -->
<div class="image-box"></div>
```

```css
.image-box {
  width: 70%;
  height: 300px; /* Второй блок будет высотой 300 пикселей. Всегда */
  border: 1px solid red;
  background: url("../images/eyes.png")
    no-repeat center / contain;
}

.responsive {
  height: 0; /* Первому блоку задаём нулевую высоту */
  padding-bottom: 39.375%; /* Отталкиваем нижнюю границу при помощи внутреннего отступа */
}
```

<iframe title="Адаптив через padding" src="../demos/adaptive.html"></iframe>

🛠 Попробуй менять размеры окна браузера и понаблюдать за поведением обоих блоков. Первый будет всегда сохранять пропорции 16:9, а вот второй всегда будет высотой 300 пикселей.

<details class="article__table article__table_all-half">
  <summary>Таблица значений <code>padding-bottom</code> для разных стандартных соотношений сторон:</summary>

| Соотношение сторон | padding-bottom |
| ------------------ | -------------- |
| 16:9               | 56.25%         |
| 4:3                | 75%            |
| 3:2                | 66.66%         |
| 8:5                | 62.5%          |

</details>