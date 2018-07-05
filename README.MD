# CETEIcean Pagination Example

This example shows one possible approach to paginating TEI documents rendered with [CETEIcean](https://github.com/TEIC/CETEIcean).

It uses [`document.createTreeWalker()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createTreeWalker) to hide **text content** inside `<tei:text>` before the nth `<tei:pb/>` and after the following `<tei:pb/>`.

## Gotchas

* We assume the first `<tei:pb/>` is placed at the beginnig of the document (pb stands for 'page beginning').
* If no `<tei:pb/>` is present, we show the whole document.
* The content of text nodes is copied to a new property on the HTML text node object. This is a bit of a hack, but works for this example

## Suggestions for integration

This code is mostly meant as an example rather than being capable to work in production. In particular, we would suggest using a framework to manage the navigation component and react to changes in data (e.g. which page is visible) as opposed to checking and updating global flags.

## License

[CC0](https://creativecommons.org/share-your-work/public-domain/)