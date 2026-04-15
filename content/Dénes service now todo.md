- [x] wrap everything in a body tag
- [ ] bs4 pretty print the code for proper indentation
- [x] !! remove all id attributes from tags
- [x] !! strip all `style` attributes that we do not use
- [x] !! remove all `<br />` tags
- [ ] (maybe later) replace `pre` tags with the native flare code snippets
- [x] !! remove all `<hr />`
- [ ] (maybe manual) `<figure>` and `<figcaption>` doodoo
- [x] all not `<span class="Code">` ought to be removed
- [x] !! remove all `<li class=...>`
- [x] replace all `<div class="alert alert">` with `<div class="Note">`
- [x] replace `<code>` tags with `span.Code`
- [x] fix all malformed html
- [x] remove `dir="ltr"` and all other meaningless attributes
- [x] strong tags -> b.UI tags

- [ ] could add a PR check if prettier passes (maybe with our custom prettier.rc)

