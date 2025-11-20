+++
title = "LaTeX Typesetting Tips"
# date = "2016-09-10"
+++

Here are a few tips to get your documents prepared in LaTeX looking even better. When you were told about LaTeX, you were likely told you would never have to worry about formatting and writing references again: LaTeX would do all of it for you. Well, LaTeX tries to, but it follows your instructions. Here are a few guidelines for giving instructions to LaTeX in a way that results in more pleasant documents.

<!--more-->

## General LaTeX behavior

Before we start, let me tell you a few details about LaTeX behavior. LaTeX typesets text for you following several typesetting considerations for aesthetics and readability, including, at least:

1. The amount and variability of [kerning][xkcd-kerning] in a paragraph: we want words and characters to be equally spaced across the paragraph,
2. The number of lines ending with hyphenation: we do not want many lines ending in hyphenation in a row,
3. The number of characters in the last line of the paragraph: we do not want the last line to be very short ([widow lines][wiki-widows]);
4. The number of lines in a paragraph before and after a page or column break: we want at least two lines before or after a page or column break (avoid [orphan lines][wiki-widows]);
5. The amount of floats in a page: we do not want a lot of floats (figures, tables, and the like) and few text on a page.

[xkcd-kerning]: https://xkcd.com/1015/
[wiki-widows]: https://en.wikipedia.org/wiki/Widows_and_orphans

LaTeX takes your text and runs it through an optimization problem to maximize "goodness" that includes the previous considerations. Overall, LaTeX tries to turn your text into something like The Art of Computer Programming.[^1]

However, it turns out that sometimes your text cannot be typeset in a way that satisfies all aesthetics and readability considerations. You should check at least for orphan lines (consideration 4 above), but I would strongly recommend you avoid widow lines as well (consideration 3). When you have a widow or an orphan line, edit your text. Yes, I said *edit your text*. [Just do it!](https://youtu.be/UhRXn2NRiWI?t=39) Either add or remove words to make the text shorter or longer and solve the problem. (Needless to say, make the text better while editing it.)

## Figures

Another thing you should take care of is figure placement (consideration 5 above). Here are a few broad recommendations:

* Place figures and tables at the top of a text column using the `[t]` placement hint. This saves space and reduces the possible number of orphans you can have. An exception to this are floats like algorithms, which we may want to have running with the text.
* LaTeX prefers to place figures after their definition in the source. If you ask LaTeX to place a figure at the top of a column, the figure might only show up in the next column. This behavior is aggravated for figures that span multiple columns (`\begin{figure*}`), which only show up on the next page. To have the figures show together with the text that discusses them, you might need to move the definition of the figure earlier in your LaTeX source file. (A bit cumbersome, but still better than changing pages to look at a figure discussed in another page.)

## Hyphens, en-dashes, and em-dashes

We have three different dashes in writing text, each with different purposes in text. The hyphen is used in word hyphenization[^2], numbers (e.g., forty-two), and compound words (e.g., plain-text). This is the key to the right of zero in US ANSI keyboards, and it is also an ASCII character, so you can just type it whenever needed.

The *en-dash* is a dash that is longer than a hyphen. It should be used for ranges (e.g., pages 3–6).  In LaTeX, you should type *en-dashes* as two consecutive hyphens (`--`) to avoid confusion, as they can look very similar to hyphens in monospaced fonts.

Finally, the *em-dash* is even longer, and is used to introduce a parenthetical.  It is best usually avoided in favor of simple commas, but might come in handy when nesting parentheticals—in combination with commas—or for very long parentheticals.  It's not on your keyboard, not on your keyboard.  The worst, however, is that the UTF-8 character is usually rendered in a single cell in monospaced fonts, which makes it *not look like it should* in plain-text documents like LaTeX.  Indead, type it in LaTeX instead by using three consecutive hyphens (`---`).  Also note that there are no spaces around *em-dashes*, you just glue them to the surrounding words—like so.

## Quotes

LaTeX does not have "smart quotes".  You have to correctly angle quotes yourself.  For left-opening single quotes use the backtick character (here are two of them because of conflicts with Markdown code blocks ` `` `). For right-closing single quotes use the quote character (`'`). For double quotes, just type two of each character.  It will look like this in LaTeX: `Please do quoting the ``right'' way`.

## Wrap-up

Overall, these instructions require little effort compared to writing of text and code, running experiments, building models, and several other activities. They are not worth skipping.

[^1]: Seriously. LaTeX and The Art of Computer Programming were made by [Don Knuth](http://www-cs-faculty.stanford.edu/~uno/). You can configure several typesetting parameters in LaTeX, but I never needed to.

[^2]: Making text look good is hard stuff; I think this is why we're stuck with LaTeX to this day.  For example, browsers are still working on it, [with Apple getting ahead of the competition with more eyecandy as usual](https://webkit.org/blog/16547/better-typography-with-text-wrap-pretty/).  Hyphenization should be a requirement for justified text; without hyphenization, consider sticking "ragged-right" (or "left-aligned") text like most of the Web.  In MS Word, do not click that "justify text" button, or search the menus on how to turn on hyphenization first (I know the option exists).
