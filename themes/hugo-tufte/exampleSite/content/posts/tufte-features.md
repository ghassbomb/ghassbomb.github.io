---
author: Totally famous person
date: '2023-04-16T16:03:45+0100'
title: The big old test page
subtitle: Fancy Subtitle
meta: true
math: true
toc: true
# hideDate: true
# hideReadTime: true
categories: [katex, latex, tufte-css]
description: "If the description field is not empty, its contents will show in the home page instead of the first 140 characters of the post."
---

## New features

### Emoji

Powered by [Noto Emoji font](https://emojipedia.org/noto-emoji/).

We really like cats. Yes, they are fluffy and happy. 🐈🐱

🪷🫶🤍😊💀🔥


### Button

{{< button
style="primary"
icon="✅"
href="javascript:javascript:(function(){function checkFrames(w) {try {var inputs = w.document.getElementsByTagName('input');for (var i=0; i < inputs.length; i++) {if (inputs[i].type && inputs[i].type == 'checkbox'){inputs[i].checked = true;}}} catch (e){}if(w.frames && w.frames.length>0){for(var i=0;i<w .frames.length;i++){var fr=w.frames[i];checkFrames(fr);}}}checkFrames(window);})()"
>}}
Open all notes
{{< /button >}}

{{< button
style="primary"
icon="❎"
href="javascript:javascript:(function(){function checkFrames(w) {try {var inputs = w.document.getElementsByTagName('input');for (var i=0; i < inputs.length; i++) {if (inputs[i].type && inputs[i].type == 'checkbox'){inputs[i].checked = false;}}} catch (e){}if(w.frames && w.frames.length>0){for(var i=0;i<w .frames.length;i++){var fr=w.frames[i];checkFrames(fr);}}}checkFrames(window);})()"
>}}
Close all notes
{{< /button >}}

{{< button
style="primary"
icon="🔄"
href="javascript:javascript:(function(){function checkFrames(w) {try {var inputs = w.document.getElementsByTagName('input');for (var i=0; i < inputs.length; i++) {if (inputs[i].type && inputs[i].type == 'checkbox'){inputs[i].checked = !inputs[i].checked;}}} catch (e){}if(w.frames && w.frames.length>0){for(var i=0;i<w .frames.length;i++){var fr=w.frames[i];checkFrames(fr);}}}checkFrames(window);})()"
>}}
Toggle all notes
{{< /button >}}

```html
{{</* button
style="primary"
icon="🔄"
href="javascript:javascript:(function(){function checkFrames(w) {try {var inputs = w.document.getElementsByTagName('input');for (var i=0; i < inputs.length; i++) {if (inputs[i].type && inputs[i].type == 'checkbox'){inputs[i].checked = !inputs[i].checked;}}} catch (e){}if(w.frames && w.frames.length>0){for(var i=0;i<w .frames.length;i++){var fr=w.frames[i];checkFrames(fr);}}}checkFrames(window);})()"
*/>}}
Toggle all notes
{{</* /button */>}}
```


### Cols (with `lang` option)

Certain things do not work with this shortcode layout, for example, Markdown's default footnote (like `[^1]`).

{{< cols "zh-Hans,en,ja" >}}
我是一个懒人。 {{< marginnote >}}这是一个边注。在屏幕很小的时候，它有一个可以点击展开的按钮。{{< /marginnote >}}{{< marginnote ind="🐱" >}}您可以在 `config.yaml` 中修改全站按钮默认设置，也可以使用 `ind` 选项为每一个边注单独设置按钮。{{< /marginnote>}}{{< marginnote ind="⚠" >}}在这个版本中，我提升了可访问性，但不包括[用不了 `:has` 的火狐](https://caniuse.com/css-has)。{{< /marginnote>}}
||
But sometimes you just have to get your hands dirty.

This is the joy and the curse of a programmer. {{< sidenote >}}Sidenote numbers are consistent across the whole page. Good numbers.{{< /sidenote >}}
||
さらに、なんと！日本語もいけます。{{< sidenote >}}読めないのか？私は大丈夫だが。{{< /sidenote >}}
{{< /cols >}}

```html
{{</* cols "zh-Hans,en,ja" */>}}
我是一个懒人。{{</* marginnote */>}}这是一个边注。{{</* /marginnote */>}}
||
But sometimes you just have to get your hands dirty.{{</* sidenote */>}}Good numbers.{{</* /sidenote */>}}
||
読めないのか？私は大丈夫だが。
{{</* /cols */>}}
```


### YouTube-nocookie

Never again click things in the video accidentally and it opens YouTube. Oh no.

{{< youtube id="YslQ2625TR4" title="iPhone Resolution by Edward Tufte" >}}

```html
{{</* youtube id="YslQ2625TR4" title="iPhone Resolution by Edward Tufte" */>}}
````


## Tufte features

### Marginnote and sidenote

This is what you came here for. {{< marginnote >}}This is a marginnote. It has no indicators on big screens.{{< /marginnote >}} Be honest. {{< sidenote >}}This is a sidenote! It has a little number.{{< /sidenote >}}

### Epigraph

{{< epigraph author="Shawn O'Hare" cite="Math is Fun" detail="p.8" >}}
This is an example of an epigraph with some math
`$ \mathbb N \subseteq \mathbb R $`
to start the beginning of a section.
{{< /epigraph >}}

```html
{{</* epigraph author="Shawn O'Hare" cite="Math is Fun" detail="p.8" */>}}
This is an example of an epigraph with some math
`$ \mathbb N \subseteq \mathbb R $`
to start the beginning of a section.
{{</* /epigraph */>}}
```

### Blockquote

Some blockquotes.  But first, we try to manually cite via

<cite>This is between cite tags and has math: `$e^x $`</cite> {{< sidenote >}}Only use `$\KaTeX{}$`, you must.{{< /sidenote >}}

{{< blockquote author="Shawn O'Hare" cite="www.shawnohare.com" >}}
This is a blockquote with two paragraphs, that employs the
theme's `blockquote` shortcode. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
{{< /blockquote >}}

```html
{{</* blockquote author="Shawn O'Hare" cite="www.shawnohare.com" */>}}
This is a blockquote with two paragraphs, that employs the
theme's `blockquote` shortcode. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
...
{{</* /blockquote */>}}
```

### Small-caps

{{< newthought >}}Sometimes a new thought{{< /newthought >}} distinguishes a section, as here.

```html
{{</* newthought */>}}Sometimes a new thought{{</* /newthought */>}}
```

### Figure

**Regular width figure:**

{{< figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/exports-imports.png"
  title="The image title"
  label="mn-export-import"
  caption="This is the image caption."
  attr="[Image attribution](#)"
  link="link"
>}}

```html
{{</* figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/exports-imports.png"
  title="The image title"
  label="mn-export-import"
  caption="This is the image caption."
  attr="[Image attribution](#)"
  link="link"
*/>}}
```


**Margin figure:**

Margin figures appear on the margin. Highly logical.
{{< figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/rhino.png"
  type="margin"
  label="mn-rhino"
  title="The image title"
  caption="This is the image caption."
  attr="[Image attribution](https://edwardtufte.github.io/tufte-css)"
  alt="alt"
  link="#"
>}}
Very importantly, they want some text to go with them, either before or after, with only one line break.

No worries if you forgot to give your figure a `label`. Marginnote (either for figure or with figure inside) will be created if any one of the following conditions is met:

1. Has `type="margin`; or
2. Has `caption`; or
3. Has `attr`.

```html {hl_lines=[3]}
{{</* figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/rhino.png"
  type="margin"
  title="The image title"
  caption="This is the image caption."
  attr="[Image attribution](https://edwardtufte.github.io/tufte-css)"
  alt="alt"
  link="#"
*/>}}
```

**Full-width figure:**

{{< figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/napoleons-march.png"
  type="full"
  label="mn-napoleonic-wars"
  title="Napoleonic wars"
  caption="This the image caption."
  attr="[Image attribution](#)"
  alt="Napoleonic wars"
  link="#"
>}}

```html {hl_lines=[3]}
{{</* figure
  src="https://github.com/edwardtufte/tufte-css/raw/gh-pages/img/napoleons-march.png"
  type="full"
  label="mn-napoleonic-wars"
  title="Napoleonic wars"
  caption="This the image caption."
  attr="[Image attribution](#)"
  alt="Napoleonic wars"
  link="#"
*/>}}
```


## Normal Markdown tests

Begin [test file](https://gist.github.com/loikein/27ef6913386b206d1b3c18b8e93c5768)…

### Formatting

**Bold**, __bold__, **加粗**

*Italic*, _italic_, *斜体*

<u>Underline</u>, <underline>underline</underline>

<del>Strike</del>, <s>strike</s>, ~~strike~~, ~strike~, --strike--

<mark>Highlight</mark>, =highlight=, ==highlight==

<!-- Comments-->

Footnote[^1], footnote[^2]

[^1]: The linked footnote appears at the end of the document.

[^2]: New lines

---


### Lists

- `ul`
- Unordered list

1. `ol`
1. Ordered list

`dl`
:   `dt`
:   Description list

- [x] Task list
- [ ] Task list

### Code

Inline `code`, `` `escape` ``, and <kbd>keystroke</kbd>

```go {linenos=table,hl_lines=["2-5"],linenostart=199}
package main

import "log"

func add(x int, y int) int {
  log.Println("We are going to take the sum of two numbers, and leave a long comment.")
  return x + y
}

func main() {
  y := add(1, 2)
  log.Println(y)
}
```

Here's an example without line numbers. 

```go {hl_lines=["2-5"],linenostart=199}
package main

import "log"

func add(x int, y int) int {
  log.Println("We are going to take the sum of two numbers, and leave a very very very long comment.")
  return x + y
}

func main() {
  y := add(1, 2)
  log.Println(y)
}
```

### Font

> 我能体に傷つけないで吞下 259 ml glass。

> Four score and seven years ago our fathers brought forth upon this continent, a new nation, conceived in Liberty, and dedicated to the proposition that all men are created equal.

0 Oo Ii Ll 1 | 2 Z 5 s 8 Bb 6 # * ^ ~ \(\) {} \[\] . , : ; “ ‘ ’ \`

```
0 Oo Ii Ll 1 | 2 Z 5 s 8 Bb 6 # * ^ ~ () {} [] . , : ; “ ‘ ’ `
```

### Inline HTML

ref: https://burk.io/2020/let-there-be-dark

<div title="#282a36" style="height: 50px; width: 100px; background-color: #282a36; display: inline-block; border-style: solid; border-color: black; color:white; padding:10px;">#282a36</div>

<div title="#f8f8f2" style="height: 50px; width: 100px; background-color: #f8f8f2; margin-right: 5px; display: inline-block; border-style: solid; border-color: black; color:black; padding:10px;">#f8f8f2</div>

### LaTeX & Table

`$\LaTeX{}$`

`$$R_1 \begin{cases} >\mu_{2} \\ \leq \mu_{2} \end{cases}$$`

| Message to agent 1 | `$M_1$`          |
| ------------------ | -------------- |
| Agent 1's action   | `$a_1$`          |
| New finding        | `$R_1 \begin{cases} >\mu_{2} \\ \leq \mu_{2} \end{cases}$` |
