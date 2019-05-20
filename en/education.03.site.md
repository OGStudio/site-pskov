Title: Education: 03. Site
Date: 2019-05-14 00:00
Category: Page
Slug: education.03.site
Lang: en

| < Back | Index | Next > |
|---|---|---|
| [02. Dependencies][prev] | [Education][index] | [04. Language][next] |

</div><div class="contents">

In this document we create a simple static web site with two pages.

Estimated completion time: ? minutes.

**Table of contents**

* [01. Inspiration](#inspiration)
* [02. Investigate `cfg` file](#cfg)
* [03. Investigate `item.template` file](#item)
* [04. Investigate `index.md` and `cv.md` files](#md)
* [05. Launch LFSA](#lfsa)
* [06. Generate the site](#gen)

<a name="inspiration"/>

## 01. Inspiration

Suppose you are a great Russian painter named Valentin Serov. Everytime anyone wants to know about you they refer to [Wikipedia][serov]. You wake up earlier today with a distinct desire to have your very own personal web site.

You set on to create the following pages:

* About me
* Curriculum vitae (CV)

Some time later you have the following files in your [site directory][01-files]:

* cfg
* item.template
* index.md
* cv.md

Let's look at their contents closer.

<a name="cfg"/>

## 02. Investigate `cfg` file

`cfg` file has the following contents:

```
input = .
item = item.template
```

`cfg` is an [INI file][ini-file] with the following keys specified:

| Key | Description |
|---|---|
| `input` | Points to a directory where `item`'s file is located |
| `item` | Points to an HTML template file that will be used to generate HTML files out of Markdown ones |

In our case, `item.template` file is located alongside `cfg`, so we use `.` to denote current directory.

<a name="item"/>

## 03. Investigate `item.template` file

`item.template` file has the following contents:

```
<!DOCTYPE html>
<html>
    <meta charset="utf-8">
    <head>
        <style>
            - - - - Style was collapsed for brevity - - - -
        </style>
        <title>Serov</title>
    </head>
    <body>
        <div id="header">
            <strong>Serov</strong>
            <a href="index.html">About me</a>
            <a href="cv.html">CV</a>
        </div>
        <center>
            <h1>PSKOV_ITEM_TITLE</h1>
            <div class="contents">
PSKOV_ITEM_CONTENTS
            </div>
        </center>
    </body>
</html>
```

**Note**: style was collapsed for brevity.

As you can see, `item.template` is an average HTML file with two constants specified:

| PSKOV constant | Description |
|---|---|
| `PSKOV_ITEM_TITLE` | Provides title from `Title:` part of page's header section |
| `PSKOV_ITEM_CONTENTS` | Provides HTML contents generated out of Markdown contents |

**Notes**:

* other **PSKOV** constants are described later
* page's header section is described below

<a name="md"/>

## 04. Investigate `index.md` and `cv.md` files

`index.md` file has the following contents:

```
 Title: About me
 Date: 2019-05-16 00:00
 Slug: index

 Hi, my name is Valentin Serov. Here's my self-portrait:
 
 ![Valentin Serov self-portrait][serov-portrait]

 - - - - Contents were collapsed for brevity - - - -
 
 Have a look at my [CV][cv] now.

 [serov]: https://en.wikipedia.org/wiki/Valentin_Serov
 [revolution]: https://en.wikipedia.org/wiki/Russian_Revolution
 [serov-portrait]: myself.jpg
 [serov-work]: mywork.jpg
 [girl-with-peaches]: https://en.wikipedia.org/wiki/Girl_with_Peaches
 [pskov]: http://opengamestudio.org/pskov
 [cv]: cv.html
```

`index.md` starts with a so-called header section:

| Header constant | Description |
|---|---|
| `Title:` | Provides value for `PSKOV_ITEM_TITLE` constant when generating HTML out of Markdown |
| `Date:` | Provides value for `PSKOV_ITEM_DATE` constant when generating HTML out of Markdown |
| `Slug:` | Tells **PSKOV** that this particular Markdown file should be saved under `<slug>.html` filename |

The rest of `index.md` contents is what any Markdown file looks like.

**Note**: make sure other pages are referenced with `html` extension, not `md` one: have a look at `[cv]` link above.

`cv.md` file has the following contents:

```
 Title: Curriculum vitae
 Date: 2019-05-16 00:00
 Slug: cv
 
 Here's my CV in case my paintings still interest you. I took a bit of a modern IT approach to structure my CV as key-value pairs of a dictionary (map), enjoy!
 
 | Key | Value |
 |---|---|
 | Name | Valentin Serov |
 | Age | 46 |
 | Marital status | Married |
 | Country | Russian Empire |
 | Alma mater | Imperial Academy of Arts |
 | Education | * Member Academy of Arts (1898) <br> * Full Member Academy of Arts (1903) |
```

As you can see, there's nothing new in `cv.md` except for a Markdown table.

<a name="lfsa"/>

## 05. Launch LFSA

Launch LFSA so that it points to directory with the files we just observed:

```
$ /path/to/local-file-system-access /path/to/dir/01.Pages
```

You should see output similar to this:

```
DIR: '/Users/kornerr/p/site-pskov-sample/01.Pages'
PORT: '8000'
```

<a name="gen"/>

## 06. Generate the site

Now it's finally time to generate your personal web site:

* Go to [Tool][tool] page
* Make sure
    * `Path:` points to the same directory you specified before
    * `Input directory:` and `Item template:` have values from `cfg`
* Press `Generate` button
* Open generated `index.html` from the site's directory locally
* You should see your web site running locally

Take time to observe your new shiny personal web site consisting of two pages.

</div><div class="contents">

| < Back | Index | Next > |
|---|---|---|
| [02. Dependencies][prev] | [Education][index] | [04. Language][next] |

[index]: education.html
[prev]: education.02.deps.html
[next]: education.04.lang.html

[01-files]: https://github.com/OGStudio/site-pskov-sample/tree/master/01.Pages
[ini-file]: https://en.wikipedia.org/wiki/INI_file
[lfsa]: http://opengamestudio.org/lfsa
[serov]: https://en.wikipedia.org/wiki/Valentin_Serov
[tool]: http://opengamestudio.org/pskov
