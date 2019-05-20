Title: Education: 02. Dependencies
Date: 2019-05-14 00:00
Category: Page
Slug: education.02.deps
Lang: en

| < Back | Index | Next > |
|---|---|---|
| [01. Why][prev] | [Education][index] | [03. Site][next] |

</div><div class="contents">

In this document we teach how to install **PSKOV** dependencies.

Estimated completion time: ?? minutes.

**Table of contents**

* [01. Dependencies](#deps)
* [02. Install LFSA](#lfsa)
* [03. Showdown](#showdown)

<a name="deps"/>

## 01. Dependencies

We designed **PSKOV** to run inside web browsers. Hence, here is a list of **PSKOV dependencies**:

| № | Dependency | Note |
|---|---|---|
| 1 | Web browser of 2010 or newer | **PSKOV** needs ECMAScript 5 (2009), any modern web browser should work |
| 2 | Local file system access (LFSA) | [LFSA][lfsa] gives **PSKOV** access to your local file system |

Since **PSKOV** is a client side JavaScript application, it has no direct access to your local file system to generate files. That's why we have also created [LFSA][lfsa], a tiny Python server to provide read/write access to your local file system at 8000 port. LFSA is under 200 lines of code, feel free to [inspect it][lfsa-src] to make sure we don't steal your data.

<a name="lfsa"/>

## 02. Install LFSA

TODO 

<a name="showdown"/>

## 03. Showdown

Tell Showdown.JS is used to convert Markdown to HTML, so users should refer to Showdown.JS for rules.


</div><div class="contents">

| < Back | Index | Next > |
|---|---|---|
| [01. Why][prev] | [Education][index] | [03. Site][next] |

[index]: education.html
[prev]: education.01.why.html
[next]: education.03.site.html

[lfsa]: http://opengamestudio.org/lfsa
[lfsa-src]: TODO-LFSA-SRC
