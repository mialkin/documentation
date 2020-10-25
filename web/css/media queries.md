# CSS media queries

Задает ширину viewport, плотность пикселей, поддержку каких-то технологий, в том числе технологий доступности (accessibility)

При ширине экрана меньше 400 пикселей соответствующие размеры шрифта для заголовка и подзаголовка должны быть:

```css
@media (max-width: 400px) {
    .header__title {
        font-size: 36px;
    }

    .header__sub-title {
        font-size: 21px;
    }
}
```

## @ true

At true начинается с ключевого слова `at media`. Дальше идет условие применения стиля, которое состоит из 2 частей, в котором первую можно опускать — это указание медиа-носителя — screen, print, speech, их там 6 разных типов. Далее идет условие, которое накладывается в данном случае на `screen`:

```css
@media screen and (max-width: 400px) {
    .header__title {
        font-size: 36px;
    }
}
```

Когда применять: включаете режим нативной верстки, потихонечку уменьшаете размер viewport и смотрите, когда начинает "сыпаться" верстка — значит пора применить media query.