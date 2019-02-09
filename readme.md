# Картонбокс ([Демо](http://cartonbox.constlab.ru/))

> [Текущая версия](https://github.com/constlab/cartonbox/releases/latest): 1.5.4 (17 февраля 2017 года ([история версий](https://github.com/constlab/cartonbox/releases)))

Джейквери-плагин для вывода фотографий, блоков с контентом и айфреймов в красивых модальных окнах, которые можно группировать, создавая, например, фото- или видео галереи.

Основное отличие от существующих подобных плагинов — правильная работа скролла на любых устройствах. При открытом модальном окне основное содержимое страницы, если оно имело полосу прокрутки, не прокручивается и никак не реагирует на скролл колесом мыши или на нажатие кнопок прокрутки на клавиатуре.

## Быстрый старт

Подключаем [Джейквери](https://jquery.com/) и [Картонбокс](https://github.com/constlab/cartonbox/releases/latest):

```html
<script src="jquery.min.js"></script>
<script src="cartonbox.min.js"></script>
<link href="cartonbox.min.css" rel="stylesheet">
```

Либо через npm:

```shell
npm install cartonbox --save
```

Добавляем к ссылке класс `.cartonbox` и, если это ссылка на картинку, параметр `data-cb-type="img"`:

```html
<a href="image.jpg" class="cartonbox" data-cb-type="img"> ... </a>
```

Либо если это ссылка на блок с контентом или сторонний сайт, то параметры `data-cb-type="inline"` и `data-cb-type="iframe"`, соответственно:

```html
<a href="#text" class="cartonbox" data-cb-type="inline"> ... </a>
<a href="https://apple.com/" class="cartonbox" data-cb-type="iframe"> ... </a>
```

Для блока с контентом в теле ХТМЛ-страницы должен присутствовать элемент с `id="text"` (такой же как название ссылки без хештега) и содержимым, которое отобразится в модальном окне, например:

```html
<div style="display: none;">
    <div id="text">
        ... ХТМЛ-код ...
    </div>
</div>
```

Инициализация:

```js
(function($) {
    $.cartonbox();
})(jQuery);
```
