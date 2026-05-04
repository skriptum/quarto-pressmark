# Quarto for Academics

Some tips for scientists creating a personal website

Author

[Quarto Pressmark](https://mdwm.org/quarto-pressmark)

Published

April 1, 2026

## On this page

- [Citable Articles](#citable-articles)
- [Google Scholar](#google-scholar)
- [JSON-LD](#json-ld)

![](library.png)

New York Public Library Floor Plan

## Citable Articles

In Quarto, you can not only cite other works with the `@bibkey` notation, e.g Einstein ([1905](#ref-einstein1905)) or Turing ([1936](#ref-turing1936)), but you can also create citeable articles.

For example, you can create a citation pattern for others to copy by inserting the `citation` keyword in your YAML Frontmatter:

``` yaml
title: Quarto for Academics
description: Some tips for scientists creating a personal website
date: "2026"
author: 
  - name: Quarto Pressmark
    url: https://mdwm.org/quarto-pressmark
citation: 
  url: https://mdwm.org/quarto-pressmark/academics
```

In the bottom of your webpage, Quarto will now automatically create a “Please cite as” and recommended BibTex Section (scroll down to [Citation](#citation) to take a look).

If you want to dig deeper into the different options for the citation, see the [Quarto Docs](https://quarto.org/docs/authoring/create-citeable-articles.html)).

## Google Scholar

And if you wan’t your work to be indexable by Google Scholar, just add a `google-scholar: true` line to your YAML. A side benefit: Tools like Zotero Browser Connectors will automatically recognize it and offer to save it for visitors to your website.

## JSON-LD

This is something I found in [Hendrik Erz’s excellent guide to Academic Websites](https://www.hendrik-erz.de/post/academic-website-v-telling-machines-who-you-are#h2-making-yourself-machine-readable-with-json-ld):

> The thing is, you can link several different Twitter accounts on your website, and while us humans can easily see which one is your personal one, a machine cannot. JSON-LD really makes it obvious to web crawlers which links between different parts of the internet exist. With JSON-LD you can show which social media profiles are yours, which organization you are a part of, and which side projects are part of you.

To create your own JSON-LD, I recommend [this easy generator](https://technicalseo.com/tools/schema-markup-generator/). After you have your Schema, just paste it into your `_quarto.yml` like this:

``` yaml
format:
  html:
    theme: [pressmark.scss]
    include-in-header: 
      text: |
        <script type="application/ld+json">
        {
          "@context": "https://schema.org/",
          "@type": "Person",
          // ETC
        </script>
```

Et voila, your website should now be much easier for machines to understand.

## References

Einstein, Albert. 1905. “On the Electrodynamics of Moving Bodies.” *Annalen Der Physik* 17: 891–921. <https://doi.org/10.1002/andp.19053221004>.

Turing, Alan M. 1936. “On Computable Numbers, with an Application to the Entscheidungsproblem.” *Proceedings of the London Mathematical Society* s2-42 (1): 230–65. <https://doi.org/10.1112/plms/s2-42.1.230>.

## Citation

BibTeX citation:

``` quarto-appendix-bibtex
@online{pressmark2026,
  author = {Pressmark, Quarto},
  title = {Quarto for {Academics}},
  date = {2026-04-01},
  url = {https://mdwm.org/quarto-pressmark/academics},
  langid = {en}
}
```

For attribution, please cite this work as:

Pressmark, Quarto. 2026. “Quarto for Academics.” April 1. <https://mdwm.org/quarto-pressmark/academics>.
