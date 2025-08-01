# ORG
Opo Regulatory Guidelines, or ORG, is a group of legal documents for wide usecases. ORG is entirely written in Markdown, contributors should know how to write in Markdown.
## Structure
ORG is structured fairly well to make it easy to browse and edit.
- /
  - Extra/
    - Antitrust
    - Brook
    - National
- Regulations.md

There is rarely a reason for a new Extra to be created, but do so if you may. Only wide-scoped things should go into the Regulations document.
## Introduction to Legaldoc
Legaldoc, shortened as ldoc, is a system used by ORG to resolve and organize dependencies of a document. As stupid as it sounds, it is helpful in many situations.

In legaldoc, the first thing of a document should be the legaldoc version, like this:<br>
`@ldv 0.1.0`<br>
###### 'ldv' stands for Legaldoc Version

Next, you can `@require` or `@import` another document. The difference is that `@require` is used to apply jurisdiction. On a document that is defined under ORG, you should `@require` ORG instead of `@import`ing it.
`@import` is better suited for use. If you are talking about an item and directly referencing things from it, you should `@import` it.

Both are used like this:<br>
`@require ORG`

`@import ORG as ORG`

In the case of the import, we can then use ORG and reference items from it like this: `ORG:[1.1A]`

When importing a group of items, or a subset within a group, we can do the following:<br>
`@import #ORG`

`@import #ORG/Extra`

We can then mention things from said documents: `ORG # Extra / National`

Legaldoc also enforces how you organize your document. While organizing a document differently does not make it invalid Legaldoc, it is recommended to structure your document like the following:
```
# [1] This is a section
## [1.1] This is a subsection
[1.1A] This is a clause
  [1.1AB] This is a directly related clause
[1.1B] This is another clause
```
That's it!
