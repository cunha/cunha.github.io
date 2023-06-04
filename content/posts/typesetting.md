+++
title = "LaTeX Typesetting Tips"
# date = "2016-09-10"
+++

Here are a few tips to get your documents prepared in LaTeX looking even better. When you were told about LaTeX, you were likely told you would never have to worry about formatting and writing references again: LaTeX would do all of it for you. Well, LaTeX tries to, but it follows your instructions. Here are a few guidelines for giving instructions to LaTeX in a way that results in more pleasant documents.

<!--more-->

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

Another thing you should take care of is figure placement (consideration 5 above). Here are a few broad recommendations:

* Place figures and tables at the top of a text column using the `[t]` placement hint. This saves space and reduces the possible number of orphans you can have. An exception to this are floats like algorithms, which we may want to have running with the text.
* LaTeX prefers to place figures after their definition in the source. If you ask LaTeX to place a figure at the top of a column, the figure might only show up in the next column. This behavior is aggravated for figures that span multiple columns (`\begin{figure*}`), which only show up on the next page. To have the figures show together with the text that discusses them, you might need to move the definition of the figure earlier in your LaTeX source file. (A bit cumbersome, but still better than changing pages to look at a figure discussed in another page.)

Overall, these instructions require little effort compared to writing of text and code, running experiments, building models, and several other activities. Doesn’t seem worth skipping.

[^1]: Seriously. LaTeX and The Art of Computer Programming were made by [Don Knuth](http://www-cs-faculty.stanford.edu/~uno/). You can configure several typesetting parameters in LaTeX, but I never needed to.
