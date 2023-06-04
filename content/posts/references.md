+++
title = "Normalizing References"
# date = "2015-06-10"
+++

Citing sources and previous work is integral to research. Here are a few tips on getting your references right when using BibTeX, although you may use the formatting rules with whatever system you use.

<!--more-->

Note these are broad recommendations that I believe will apply to your papers. If you think this is overkill, go check the hundreds of pages the [Chicago Manual of Style](https://www.chicagomanualofstyle.org/home.html) has on references, including how to cite cooking recipes, blueprints, songs, papers in foreign languages, and whatever you can think of.

## Keep your references in a single place

You will likely have to cite the same related work on multiple papers, so just keep all your references around in *one* place. Keeping them in one place might have other uses, like helping you find a paper you've read in the past but don't remember the title or authors. Whenever I start a new paper, I link (with `ln -s`) my BibTeX file to the paper's directory. Any new references I read and cite will be available in the BibTeX file for my next papers. If you like to go turbo, you may use a reference management system; I haven't got there yet.

## What to show

References should be consistent, and by consistency I mean that you should show the same items of information for all conference papers, and similarly for all journal papers. I settled on the minimum amount of information that allows a reader to unambiguously find the cited paper. Using the minimum makes it easier for you to create the BibTeX entry and minimizes use of space, which helps whenever submissions are subject to page limits.

For conference articles I show exactly: authors, title, conference, and year. In BibTeX source files, everything outside entries is considered a comment, so you can just move all additional information that is not one of these four items outside the entry and keep them around for later reference. Here is an example entry in my BibTeX file:

```bibtex
@inproceedings{sundaresan13bottleneck,
    author = {Sundaresan, S. and Feamster, N. and
              Teixeira, R. and Magharei, N.},
    title = {{Measuring and Mitigating Web Performance
              Bottlenecks in Broadband Access Networks}},
    booktitle = IMC,
    year = {2013},
}
 isbn = {978-1-4503-1953-9},
 location = {Barcelona, Spain},
 pages = {213--226},
 numpages = {14},
 url = {http://doi.acm.org/10.1145/2504730.2504741},
 doi = {10.1145/2504730.2504741},
 acmid = {2504741},
 publisher = {ACM},
 address = {New York, NY, USA},
 keywords = {DNS prefetching, bottlenecks, broadband networks},
```

For journal articles I show exactly: authors, title, journal, volume, number, pages, and year. Here is an example entry:

```bibtex
@article{roughan11astopo,
   author = {Roughan, M. and Willinger, W. and Maennel, O. and
             Perouli, D. and Bush, R.},
   journal = IEEEJSAC,
   title = {{10 Lessons from 10 Years of Measuring and Modeling
             the Internet's Autonomous Systems}},
   year = {2011},
   volume = {29},
   number = {9},
   pages = {1810--1821}
}
 month={October},
 keywords={Internet;routing protocols},
 doi={10.1109/JSAC.2011.111006},
 ISSN={0733-8716},}
```

## Use consistent formatting and abbreviations

The Chicago Manual of Style recommends we capitalize titles (and section headers). Once you invest time in learning how to capitalize titles, you will get it right, and it will look better too! Note that BibTeX removes capitalization from titles by default (a desperate attempt at consistent capitalization?), so you need to add two opening and closing braces to let BibTeX know you are a pro! Check the examples above.

Normalize conference and journal names. To avoid having conferences and journals appear differently across multiple papers, you can create aliases for them. In the example above I use "IMC" and "IEEEJSAC" as the conference and journal names, respectively.  These values are defined earlier in my BibTeX file as follows:

```bibtex
@string{IMC = "Proc. ACM IMC"}
@string{IEEEJSAC = "IEEE J. Selected Areas in Communications"}
```

This last bit is controversial, but I do abbreviate first names. My reasoning is that abbreviating first names saves space and makes it easy to be consistent across all papers. Omitting authors using "et al." is rare in computer networking and related areas, I would recommend you avoid it.
