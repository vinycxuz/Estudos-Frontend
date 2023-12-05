
## Describe the difference between `<script>`, `<script async>` and `<script defer>`

`<script>` tags are used to include JavaScript on a web page. The `async` and `defer` attributes are used to change how/when the loading and execution of the script happens.

## Plain `<script>`

For normal `<script>` tags without any `async` or `defer`, when they are encountered, HTML parsing is blocked, the script is fetched and executed immediately. HTML parsing resumes after the script is executed.

## `<script async>`

In `<script async>`, the script will be fetched in parallel to HTML parsing and executed as soon as it is available (potentially before HTML parsing completes) and it will not necessarily be executed in the order in which it appears in the HTML document. Use `async` when the script is independent of any other scripts on the page, for example, analytics.

## `<script defer>`

In `<script defer>`, the script will be fetched in parallel to HTML parsing and executed when the document has been fully parsed, but before firing `DOMContentLoaded`. If there are multiple of them, each deferred script is executed in the order they appeared in the HTML document.

If a script relies on a fully-parsed DOM, the `defer` attribute will be useful in ensuring that the HTML is fully parsed before executing.

## Notes

- Generally, the `async` attribute should be used for scripts that are not critical to the initial rendering of the page and do not depend on each other, while the `defer` attribute should be used for scripts that depend on / is depended on by another script.
- The `async` and `defer` attributes are ignored for scripts that have no `src` attribute.
- `<script>`s with `defer` or `async` that contain `document.write()` will be ignored with a message like "A call to document.write() from an asynchronously-loaded external script was ignored".

## References

- [`<script>`: The Script element | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#defer)
- [async vs defer attributes](https://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)