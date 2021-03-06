Title: Обучение: 04. Язык
Date: 2019-06-25 00:00
Category: Page
Slug: education.04.lang
Lang: ru

| < Назад | Начало | Далее > |
|---|---|---|
| [03. Сайт][prev] | [Обучение][index] | [05. Блог][next] |

</div><div class="contents">

В этом документе мы добавим выбор языка.

Ожидаемое время завершения: 10 минут.

**Содержание**

* [01. Локализация](#localization)
* [02. Изучите файл `pskov.cfg`](#cfg)
* [03. Изучите файлы шаблонов](#item)
* [04. Изучите файлы Markdown](#md)
* [05. Запустите ЛФСД](#lfsa)
* [06. Сгенерируйте сайт](#gen)
* [07. Проверьте сайт](#observe)
* [08. Итог](#summary)

<a name="localization"/>

## 01. Локализация

Теперь, когда у вас есть собственный веб-сайт на английском, вы задумываетесь о русской версии, ведь вы же всё-таки русский!

Вы создаёте директорию со [следующей структурой файлов][02-files]:

* `pskov.cfg`
* `en/item.template`
* `en/about.md`
* `en/cv.md`
* `ru/item.template`
* `ru/about.md`
* `ru/cv.md`

Давайте взглянем на содержимое этих файлов.

<a name="cfg"/>

## 02. Изучите файл `pskov.cfg`

Файл `pskov.cfg` содержит следующее:

```
input = en;ru
item = item.template
```

Как видите, `input` может принимать несколько директорий, разделённых символом `;`. **ПСКОВ** обработает каждую указанную директорию так же, как и ранее.

В нашем случае каждая из директорий - `en/` и `ru/` - содержит собственный шаблон `item.template`.

<a name="item"/>

## 03. Изучите файлы шаблонов

* Содержимое `en/item.template`:

    ```
    - - - - Схлопнуто для краткости - - - -
            <title>Serov</title>
        </head>
        <body>
            <div id="header">
                <strong>Serov</strong>
                <a href="about.html">About me</a>
                <a href="cv.html">CV</a>
                <div id="lang">
                    <a href="../en/PSKOV_ITEM_URL">EN</a>
                    <a href="../ru/PSKOV_ITEM_URL">RU</a>
                </div>
            </div>
            <center>
    - - - - Схлопнуто для краткости - - - -
    ```
* Содержимое `ru/item.template`:

    ```
    - - - - Схлопнуто для краткости - - - -
            <title>Серов</title>
        </head>
        <body>
            <div id="header">
                <strong>Серов</strong>
                <a href="about.html">Обо мне</a>
                <a href="cv.html">Резюме</a>
                <div id="lang">
                    <a href="../en/PSKOV_ITEM_URL">EN</a>
                    <a href="../ru/PSKOV_ITEM_URL">RU</a>
                </div>
            </div>
            <center>
    - - - - Схлопнуто для краткости - - - -
    ``` 

**Внимание**: начало и конец схлопнуты для краткости.

Как видите, `en/item.template` и `ru/item.template` очень похожи на [виденный ранее][prev] `item.template`.

Изменения следующие:

* использование секции `<div id="lang">...</div>` для отображения выбора языка
* локализация заголовков на Английском и Русском языках

Выбор языка использует следующую новую константу **ПСКОВА**:

| Константа ПСКОВА | Описание |
|---|---|
| `PSKOV_ITEM_URL` | Предоставляет имя файла генерируемой страницы |

Использование `PSKOV_ITEM_URL` даёт вам поддержку стольких языков, сколько пожелаете.

<a name="md"/>

## 04. Изучите файлы Markdown

Файлы `en/about.md` и `en/cv.md` выглядят почти идентично [виденным ранее][prev]. `ru/about.md` и `ru/cv.md` представляют собой русские версии соответствующих английских страниц.

Например, `ru/cv.md` содержит:

```
 Title: Резюме
 Slug: cv

 Здесь вы можете увидеть моё резюме в том случае, если мои произведения всё ещё вас интересуют. Я использовал современный подход ИТ для структурирования своего резюме в виде пар ключ-значение словаря (карты). Наслаждайтесь!

 | Ключ | Значение |
 |---|---|
 | Имя | Валентин Серов |
 | Возраст | 46 |
 | Семейное положение | Женат |
 | Страна | Российская Империя |
 | Учёба | Императорская Академия художеств |
 | Звания | * академик ИАХ (1898) <br> * действительный член ИАХ (1903) |
```

**Внимание**: русская страница использует точно такое же значение `Slug`, как и английская страница.

<a name="lfsa"/>

## 05. Запустите ЛФСД

<video controls poster="../vid/education.04.lang.launch-lfsa.edgy.poster.png">
    <source src="../vid/education.04.lang.launch-lfsa.edgy.mp4" type ="video/mp4">
    <source src="../vid/education.04.lang.launch-lfsa.edgy.webm" type ="video/webm">
    ОШИБКА Ваш браузер не поддерживает видео HTML5
</video>

Запустите [ЛФСД][lfsa] с указанием директории, содержащей только что рассмотренные файлы:

```
$ /путь/до/lfsa_1.0.0.py /путь/до/директории/02.Language
```

<a name="gen"/>

## 06. Сгенерируйте сайт

<video controls poster="../vid/education.04.lang.gen.edgy.poster+ru.png">
    <source src="../vid/education.04.lang.gen.edgy+ru.mp4" type ="video/mp4">
    <source src="../vid/education.04.lang.gen.edgy+ru.webm" type ="video/webm">
    ОШИБКА Ваш браузер не поддерживает видео HTML5
</video>

Перейдите на страницу [Инструмент][tool] и нажмите кнопку `Генерировать` для генерации файлов HTML рядом с файлами Markdown.

<a name="observe"/>

## 07. Проверьте сайт

<video controls poster="../vid/education.04.lang.observe.edgy.poster+ru.png">
    <source src="../vid/education.04.lang.observe.edgy.mp4" type ="video/mp4">
    <source src="../vid/education.04.lang.observe.edgy.webm" type ="video/webm">
    ОШИБКА Ваш браузер не поддерживает видео HTML5
</video>

Проверьте сгенерированный веб-сайт локально: откройте файл `ru/about.html` или `en/about.html` и переключите язык.

<a name="summary"/>

## 08. Итог

Вы успешно добавили выбор языка. [Проверьте результат][02-sample].

Представлены константы **ПСКОВА**:

| Константа ПСКОВА | Описание |
|---|---|
| `PSKOV_ITEM_URL` | Предоставляет имя файла генерируемой страницы |

</div><div class="contents">

| < Назад | Начало | Далее > |
|---|---|---|
| [03. Сайт][prev] | [Обучение][index] | [05. Блог][next] |

[index]: education.html
[prev]: education.03.site.html
[next]: education.05.blog.html

[02-files]: https://github.com/OGStudio/site-pskov-sample/tree/master/02.Language
[02-sample]: http://opengamestudio.org/pskov/sample/02.Language/ru/about.html
[lfsa]: http://opengamestudio.org/lfsa/ru
[tool]: http://opengamestudio.org/pskov/ru/pskov_1.0.0+ru.html
