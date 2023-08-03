---
title: "Web Typography: A Compiled Guide"
date: 2023-08-03T16:50:44+05:00
author: "Ghassan Shahzad"
categories: 
  - Guide
tags:
  - Design
  - Typography
  - Web Design
draft: false
summary: In which I compile multiple books, and dozens of articles, worth of web typography wisdom.
pinned: true
---

## Introduction
> Perfect typography is more science than an art \
— Jan Tschichold

Typography is the most important part of design—web or print—by a long-shot. Changing the way words *look* changes the way the words are *perceived*. If your type is a chore to read, or obnoxious to look at, most would prefer to simply click off.[^1] And, in a time where the average user only has *this* much of an attention span, capturing his interest with beautiful typography is a practical necessity. You could even say that [web design is 95% typography.](https://ia.net/topics/the-web-is-all-about-typography-period)

This ‘guide’ is a labor for which I’ve consulted [**3 books and dozens of articles**](#bibliography), and which I plan to continuously update.

### Some Clarifications
- A typeface is a family of related ‘fonts’, of the same style, whereas a font is the *individual* variations—bold, italic, regular—of a single font in that family. So, for example, Helvetica is a typeface, whereas Helvetica Italic or Helvetica Regular is a font.
- Type colour refers to the *contrast* of a font (usually coloured black on a white background)—not its actual color. Low contrast fonts are usually thicker or heavier, whereas higher contrast fonts look lighter.
- The two main groups of typeface styles are serif and sans-serif. Serif styles are further divided into old style, transitional, neo-classical, slab and didone. Sans-serif typeface styles are grotesque, geometric and humanistic.
- Choosing a typeface is really not as important as choosing how to *present* it.
- Make sure to set `text-rendering: optimizeLegibility;` to enable kerning, which is generally always good.
- Finally, none of these rules are on a must-follow basis. Just use them as guidelines.


## Choosing a Typeface
To pick a typeface, you must clarify certain priorities:

1. What is the *goal* of your website? Is it a blog?
2. What *kind* of text does it involve? Technical?
3. What would the *audience* most like? Programmers might like monospace, for example.
4. Are you planning one typeface to rule them all, or a combination of typefaces?
5. Your fonts *should* come in nine-weights from Thin (100)-> Black (900), and the three styles: normal, italic, and oblique.
6. Font size is important—a nice font, but one that takes seconds to load, is not worth it.
7. Choose the OpenType (.otf) typeface over the non-OpenType typeface. OpenType typefaces have cross-platform compatibility, all fonts in a single file, larger character sets and extensive language support. They also often support *advanced typographic features* like ligatures, small caps, fractions, and figures.

## The Meat

> Typography has one plain duty before it and that is to convey information in writing. No argument or consideration can absolve typography from this duty. A printed work which cannot be read becomes a product without purpose.\
— Emil Ruder

### Type Size
A rule is to set the type size of body text at the same size that the text of a book held at arms-length appears. This essentially translates to 16px for mobile (Rutter, 2017), and from 18-22px for desktop (Latin, 2019) or 15-25px (Butterick, 2013), but typefaces differ in actual size because of various factors such as x-height, weight, and the need to accommodate characters from different languages. You can game this by adjusting x-heights, or ‘aspect heights’ as CSS calls them.

### Line Length
*Don’t* keep your lines too long. Our eyes need breaks, for which we utilize line breaks. Lines too long will tire our eyes out. Keep the width between 45-75 characters (23-38ems) (Latin, 2019 and Rutter 2017). A rule is to be able to fit between 2-3 entire alphabets in your line (Butterick, 2013). The easiest way to do this is to use the `p` selector and the `max-width` property like:

```css
p {
	max-width: 25em;
}
```

### Line Height/Spacing
Line height is evenly distributed below and above a line of text. In the letterpress age, strips of lead were used to separate lines (hence the term ‘leading’, for space between lines AND the type size combined). This shows that lots of factors should affect your choice of line height—the length of lines, the type size, the type colour, and even the typeface. If your typeface is heavier or larger, generally, you set the line height higher to make up for it. This could be 1.3-1.6x the type size (Latin, 2019), or 120-145% the type size (Butterick, 2013). You should use unit-less multipliers for `line-height` properties, like: `line-height: 1.5;`. You can, in-fact, also do as your predecessors and set leading like:

```css
p {
	font: 15px/1.5 sans-serif;
}
```
same as
```css
p {
	font-size: 15px;
	line-height: 1.5;
	font-family: sans-serif;
}
```

Headings need a line-height of 1-1.2x their type size (Latin, 2019) since they are shorter.

### Letter Spacing
Letter spacing is a tool that you should not use much, except in the case of headings. For headings, applying negative letter spacing is appreciated, from 3-5% (Latin, 2019). If you have a line in small caps or all upper-case, it is also a good idea to *increase* letter-spacing by 5-10% (Latin, 2019).

### Paragraph Spacing
Paragraph spacing is the alternative to [indentation](#indentation), and is by far more common on the web. Generally, use spacing after the paragraph (not before), and set the spacing to 50-100% of the body text size (Butterick, 2013).

### Indentation
If you wish to use paragraph indentation instead of paragraph spacing for whatever reason, use the `p + p` selector and the `text-indent` property. Also, do *not* use both paragraph indentation *and* spacing simultaneously. For indentation, it should generally equal line-height (Latin, 2019) or be 1-4x the type size (Butterick, 2013).

### Justification
Web browsers handle justified text very poorly—they leave blank spaces in between words to make up for the justification. This breaks the flow of the paragraph, and thus is not agreeable to the eyes or the rhythm (Latin, 2019 and Rutter, 2017). If you decide to use justification regardless, make sure *not* to justify the final line of a paragraph like this: `p {text-align-last: justify;}`.

### Scales and Modularity
*Don’t* choose your type sizes randomly. Use modular scales. There’s the diatonic scale that uses ‘pt’s, or you can use the myriad other scales that come with css by default. The em, for example, has a long history in typography. It differs from the rem in that the rem is always relative to the *root* element, whereas the *em* is inherited from its parent div. Use the em for local-sizing within a component, and the rem for global-sizing.

To get started with your own scale:

1. Choose your base type size — the one you will use for body text
2. You now need to pick, or create, your scale. You can use the golden ratio, which basically involves multiplying the base font by 1.618 to get your header size, and going from there. There’s also the 3:2 ratio. 
3. Assuming you’re using 4 headers, a base size for paragraphs, the 3:2 ratio, and two smaller type sizes just in case, you will get something like this:   
	
<table>
<thead>
<tr>
<th>Use</th>
<th>Size (px)</th>
<th>Size (rem)</th>
</tr>
</thead>
<tbody>
<tr>
<td>H1</td>
<td>74.25px</td>
<td>3.375rem</td>
</tr>
<tr>
<td>H2</td>
<td>49.5px</td>
<td>2.25rem</td>
</tr>
<tr>
<td>H3</td>
<td>33px</td>
<td>1.5rem</td>
</tr>
<tr>
<td>H4</td>
<td>22px</td>
<td>1rem</td>
</tr>
<tr>
<td>Base</td>
<td>22px</td>
<td>1rem</td>
</tr>
<tr>
<td>Fig. Captions</td>
<td>14.5px</td>
<td>0.75rem</td>
</tr>
<tr>
<td>Small</td>
<td>9.5px</td>
<td>0.5rem</td>
</tr>
</tbody>
</table>
	
To utilise this table, we need to set the base size in our `html` selector in css with the `font-size` property. With that done, we can utilise the `rem` scale for setting the rest of our font-sizes. The benefit of this is modularity—now, you only need to change the base font size and all the other type sizes will change themselves accordingly.  You can even set the `line-height` and line length properties according to the `rem`, so that when you change your font size, the two other values also change appropriately. Don’t be afraid to bend the rules slightly, so long as it looks fine.

### Dropcaps
Dropcaps are the large letters at the beginning of paragraphs. They are partially cosmetic, but also useful signifiers for important parts. To get them in css, create the following selector in css:
```css
.dropcap {
	float: left;
	font-size: 35px;
	line-height: 30px;
	padding-right: 4px;
}
```

### Links
There is no need to go all out in indicating links. The best hyperlinks look just like text. Instead of styling (underlines, small-caps, etc.), just change the colour of the hyperlink text. The contrast ratio between the normal text-color and the hyperlink color should be 3:1 (as can be calculated [here](https://juicystudio.com/services/luminositycontrastratio.php#specify).

### Block Quotes
To format block quotes, reduce the point-size, line-spacing, and indent the block around 2-5ems. And, most of all, do *not* use these too often. Especially when quoting passages from books, ask yourself ‘can I not just summarize this?’ (Butterick, 2013).


### Punctuation

#### Dashes
There are actually three dashes: hyphen (-), en (–), and em (—). On MacOS, you get hyphen by simply pressing the dash button, get en by pressing optn+dash button, and get em by pressing optn+shift+dash button. 

In HTML, you use a thin space (&thinsp) after any em dash. The em dash is used as, alternatively:

1. A comma replacement
2. An indicator of a quote author
3. A break

The en dash is used as a replacement for ‘to’, like in indicating time: 6–7PM. Finally, the hyphen is used for hyphenating words—hence the name. *Don’t* use the hyphen for a prefix.

#### Quotation Marks
Just use smart quotes, except in actual code, of course.

### Page Layout


#### The Centred Column
Many websites, especially the blogs and other text-heavy mediums, tend to have one centred column where their body text goes, with equal-sized margins on the left and right sides. This is partly a product of a very simplistic and minimal mindset towards page layout, and also exists because it requires very little tweaking to be mobile-friendly. But do not chase after symmetry—it’s boring. Try uneven margins, or just completely align your text to the left or right (Latin, 2019). But do not be afraid of empty space. (Butterick, 2013).

#### Responsive Web Design
The ‘common sense’ position on responsive web design is to tailor your website to the *most* restrictive platform (usually, mobile), and then add on any extra features for the less restrictive platforms. In terms of type, this means tailoring your base type size to mobile screens, and slowly increasing the type size as you go up in screen size/platform. If you’ve used modular scales, all this should merely involve changing the base type size in your html selector.

When designing media queries, Rutter recommends using `rem` for the `min-width` property. This ensures that your layout adaptations are based on typographic reasoning.


## Bibliography
Rutter, R. (2017). [Web Typography: A Handbook for Designing Beautiful and Effective Typography in Responsive Websites](https://book.webtypography.net/).

Butterick, M. (2013). [Practical Typography](https://practicaltypography.com/).

Latin, M. (2019). Better Web Typography for a Better Web (Second edition).

[^1]: [‘The Aesthetics of Reading’](http://wbtyp.net/22) by Kevin Larson &
Rosalind W. Picard (2005).