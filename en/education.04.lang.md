Title: Education: 04. Language
Date: 2019-06-18 00:00
Category: Page
Slug: education.04.lang
Lang: en

| < Back | Index | Next > |
|---|---|---|
| [03. Site][prev] | [Education][index] | [05. Blog][next] |

</div><div class="contents">

In this document we add language selection.

Estimated completion time: 10 minutes.

**Table of contents**

* [01. Localization](#localization)
* [02. Investigate `pskov.cfg` file](#cfg)
* [03. Investigate template files](#item)
* [04. Investigate Markdown files](#md)
* [05. Launch LFSA and generate the site](#gen)
* [06. Summary](#summary)

<a name="localization"/>

## 01. Localization

Now that you have your web site in English you start to wonder why there's no Russian version, you're Russian after all!

You set on to create the following [directory structure][02-files]:

* `pskov.cfg`
* `en/item.template`
* `en/about.md`
* `en/cv.md`
* `ru/item.template`
* `ru/about.md`
* `ru/cv.md`

Let's look at the contents of these files closer.

<a name="cfg"/>

## 02. Investigate `pskov.cfg` file

`pskov.cfg` file has the following contents:

```
input = en;ru
item = item.template
```

As you see, `input` can accept multiple directories separated by `;` symbol: **PSKOV** will go over each directory specified and run as before.

In this case, both `en/` and `ru/` directories have their own `item.template` file.

<a name="item"/>

## 03. Investigate template files

* `en/item.template` contents:

    ```
    - - - - Collapsed for brevity - - - -
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
    - - - - Collapsed for brevity - - - -
    ```
* `ru/item.template` contents:

    ```
    - - - - Collapsed for brevity - - - -
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
    - - - - Collapsed for brevity - - - -
    ``` 

**Note**: beginning and ending were collapsed for brevity.

As you can see, both `en/item.template` and `ru/item.template` look similar to `item.template` we saw [before][prev].

The changes include:

* use of `<div id="lang">...</div>` section to present language selection
* localization of titles into English and Russian

Language selection uses new **PSKOV** constant:

| PSKOV constant | Description |
|---|---|
| `PSKOV_ITEM_URL` | Provides generated page's file name |

As you see, `PSKOV_ITEM_URL` is all you need to have your page in as many languages as you please.

<a name="md"/>

## 04. Investigate Markdown files

`en/about.md` and `en/cv.md` files look almost exactly as [before][prev]. `ru/about.md` and `ru/cv.md` are simply Russian variants of corresponding pages.

For example, `ru/cv.md` has the following contents:

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

**Note**: Russian page has exactly the same `Slug` value as English one.

<a name="gen"/>

## 05. Launch LFSA and generate the site

Launch [LFSA][lfsa] so that it points to directory with the files we just observed:

```
$ /path/to/lfsa_1.0.0.py /path/to/dir/02.Language
```

Generate the site:

* Go to [Tool][tool] page
* Press `Generate` button
* Open generated `en/about.html` or `ru/about.html` from the site's directory locally
* Switch language to verify language selection works fine

<a name="summary"/>

## 06. Summary

You have successfully added language selection. [Check out the result][02-sample].

Introduced PSKOV constants include:

| PSKOV constant | Description |
|---|---|
| `PSKOV_ITEM_URL` | Provides generated page's file name |

</div><div class="contents">

| < Back | Index | Next > |
|---|---|---|
| [03. Site][prev] | [Education][index] | [05. Blog][next] |

[index]: education.html
[prev]: education.03.site.html
[next]: education.05.blog.html

[02-files]: https://github.com/OGStudio/site-pskov-sample/tree/master/02.Language
[02-sample]: http://opengamestudio.org/pskov/sample/02.Language/en/about.html
[lfsa]: http://opengamestudio.org/lfsa
[tool]: http://opengamestudio.org/pskov
