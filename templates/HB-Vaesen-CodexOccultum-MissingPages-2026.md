```metadata
title: Vaesen - Codex Occultum - Missing Pages
description: >-
  This is a template to add pages to the Vaesen RPG Starter Box - Codex Occultum
  booklet
tags:
  - vaesen
  - meta:theme
renderer: V3
theme: Blank

```

```css
/*=======---  Example CSS styling  ---=======*/
/* Any CSS here will apply to your document! */
@import url('https://fonts.googleapis.com/css2?family=IM+Fell+English:ital@0;1&family=IM+Fell+French+Canon:ital@0;1&family=Mrs+Saint+Delafield&display=swap');
@import url('https://fonts.cdnfonts.com/css/prince-valiant');

*, *::before, *::after {
  box-sizing  : border-box;
}

:root {
  --color-text: #231f20;
}

.page {
  width: 148mm;
  height: 210mm;
  padding: 15mm 0;
  columns: 1;
  font-family: "IM Fell English";
  font-size: 9pt;
  text-align: justify;
  hyphens: auto;
  color: var(--color-text);
  line-height: 1.25;
  background-color: #f7f2e9;
  background-image: url(https://sibling-dex.github.io/homebrewery-templates/img/Page.png);
  background-size : 100% 100%;
  background-position: center;

  .columnWrapper {
    height: 182mm;
    width: 106mm;
    margin: auto;
    
    &:not(:has(.cover-image,.title)) {
     border: 2pt solid var(--color-text);
     padding: 6pt;
    }
    &:has(.cover-image) {
      display: grid;
      align-content: center;
    }
    &:has(.title) {
      text-align: center;
    }
  }
  .cover-image {
    width: 100%;
    box-shadow: 1px 1px 4px 0px #00000088;
    background-color: #e8e0d5;
    background-image: url(https://sibling-dex.github.io/homebrewery-templates/img/Background.png);
    background-size : 110% 110%;
    background-position: center;
    background-blend-mode: multiply;
    padding: 4mm;
  }
  h1, h2 {
    text-align: center;
    font-weight: normal;
  }
  h1 {
    font-family: "IM Fell French Canon";
    font-size: 24pt;
    text-transform: uppercase;
    border-bottom: 2pt solid var(--color-text);
    padding: 5pt 0 3pt 0;
    margin: -8pt -8pt 8pt -8pt;
    
    &.title {
      font-family: "Prince Valiant";
      font-size: 60pt;
      text-transform: none;
      letter-spacing: 0.1em;
      border: none;
    }
  }
  h2 {
    font-family: "IM Fell English";
    font-size: 12pt;
    font-style: italic;
    margin: 1em 0 .5em 0;
    
    &.subtitle {
      text-transform: uppercase;
      font-style: normal;
      letter-spacing: 0.1em;
    }
  }
  p + p {
    text-indent: 1em;
  }
  blockquote {
    font-style: italic;
    line-height: 1.5;
    margin: .75em 0 1em 0;
  }
  hr {
    border: 1pt solid var(--color-text);
    color: #222222;
    margin: 1em 0 .5em 0;
  }
  .dropcap {
    font-family: "IM Fell French Canon";
    font-size: 2.75em;
    float: left;
    margin-top: -.175em;
    margin-right: .05em;
    margin-bottom: -.2em;
  }
  .credits {
    font-size: 7pt;
    width: 116mm;
    text-align: center;
    position: absolute;
    inset: auto 0 10mm 0;
    margin: auto;
    
    p {
      margin-bottom: .5em;
    }
  }
  .note {
    display: block;
    margin: auto;
    margin-top: 1em;
    padding: 1.2em;
    background: #ede2d3;
    background-image: url(https://sibling-dex.github.io/homebrewery-templates/img/Background.png);
    background-size : 110% 110%;
    background-position: center;
    background-blend-mode: multiply;
    box-shadow: 1px 1px 4px 0px #00000088;
  }
  .handwritten {
    font-family: "Mrs Saint Delafield";
    font-size: 12pt;
  }
}



















```

# Codex  Occultum
{title}

{{width:70%
---

## The Missing Pages
{subtitle}

{{ * * *}}

> This template is made for additional entries to the Codex Occultum of the Society (former Order of Artemis).

> If you encounter a vaesen yet unknown to the Society, it is your duty to catalogue it and add the page to the codex.

> It is also the duty of every memeber of the Society to try and gather any lost entries and complete the codex.

{{ * * *}}

---
}}

{{note,width:80%
### To get the best results:
Under "Get PDF" set paper size to A5; Print at 100% scale;  
Turn on the "Background graphics" setting;  
Cut the side-margins after printing to fit the booklet.
}}

{{credits
This product was created under license. Vaesen and its logo are trademarks of Fria Ligan AB and Johan Egerkrans.

This work contains material that is copyright Fria Ligan AB, Johan Egerkrans and/or other authors. Such material is used with permission under the Community Content Agreement for Free League Workshop.

All other original material in this work is copyright [year] by [your legal name or company name] and published under the Community Content Agreement for Free League Workshop. 

This entry uses the ["Missing Pages"](https://homebrewery.naturalcrit.com/share/_066MShQBUk_) homebrewery template by Sibling Dex.

**Artwork:** ["Krampus mit Kind"](https://commons.wikimedia.org/wiki/File:1911_circa_anonymer_K%C3%BCnstler_Wiener_Werkst%C3%A4tte_Postkarte_No._542,_Krampus_mit_Kind.jpg), anonymous artist (Public Domain)
}}

\page

![](https://upload.wikimedia.org/wikipedia/commons/f/f8/1911_circa_anonymer_K%C3%BCnstler_Wiener_Werkst%C3%A4tte_Postkarte_No._542%2C_Krampus_mit_Kind.jpg){cover-image}

\page

# Krampus

{{dropcap T}}HE Krampus is a horned devil-like figure who appears during the Christmas season and aims to punish children who have been naughty and misbehaving. He is the counterpart to Saint Nicolas, who gives gifts to well-behaved children. 

There are legends of Krampus from Germany and Austria that talk about similar figures. What is certain is, that the Krampus is known in these regions as one of the commonly depicted companions of Saint Nicholas. The origins of this vaesen are unclear but some evidence points to pre-Christian origins. 

## Banishment

The most effective way known to avoid the Krampus, is to behave and be a good child throughout the year. However, once the Krampus has its sight on you, there are only two options left to you: First, you can endure the possibly harsh punishment and vow to behave in the coming year; Second, hide behind an oven for the whole of Christmas Night and make no sound to draw the Krampuses attention.

::::::

{{note,handwritten,width:80%
Austrians in the community we studied are quite aware of "heathen" elements being blended with Christian elements in the Saint Nicholas customs and in other traditional winter ceremonies. They believe Krampus derives from a pagan supernatural who was assimilated to the Christian devil.

---John Honigmann, "The Masked Face", 1977
}}

\page

### Disclaimer 
THIS TEMPLATE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH OR THE USE OR OTHER DEALINGS IN THE TEMPLATE.
{font-size:9pt}