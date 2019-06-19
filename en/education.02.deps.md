Title: Education: 02. Dependencies
Date: 2019-06-18 00:00
Category: Page
Slug: education.02.deps
Lang: en

| < Back | Index | Next > |
|---|---|---|
| [01. Why][prev] | [Education][index] | [03. Site][next] |

</div><div class="contents">

In this document we describe **PSKOV** dependencies and how to get them.

Estimated completion time: 5 minutes.

**Table of contents**

* [01. Dependencies](#deps)
* [02. Details](#details)

<a name="deps"/>

## 01. Dependencies

We designed **PSKOV** to run inside web browsers. Here is what you need to run **PSKOV**:

| № | PSKOV dependency | Notes |
|---|---|---|
| 1 | Web browser of 2010 or newer | **PSKOV** needs ECMAScript 5 (2009), any modern web browser should work |
| 2 | Local file system access | [LFSA][lfsa] gives **PSKOV** access to your local file system. Install LFSA to be able to use **PSKOV**. |

**Note**: [install LFSA][lfsa] to be able to use **PSKOV**.

<a name="details"/>

## 02. Details

**PSKOV**:

* is a client side JavaScript application
* has no direct access to local file system
* uses [LFSA][lfsa] to access local file system
* uses [Showdown][showdown] to convert Markdown to HTML

**LFSA**:

* is a tiny Python server to provide read/write access to local file system
* runs at 8000 port
* is under 200 lines of code, feel free to [inspect it][lfsa-src]

</div><div class="contents">

| < Back | Index | Next > |
|---|---|---|
| [01. Why][prev] | [Education][index] | [03. Site][next] |

[index]: education.html
[prev]: education.01.why.html
[next]: education.03.site.html

[lfsa]: http://opengamestudio.org/lfsa
[lfsa-src]: https://bitbucket.org/ogstudio/lfsa/src/default/lfsa_1.0.0.py
[showdown]: https://github.com/showdownjs/showdown
