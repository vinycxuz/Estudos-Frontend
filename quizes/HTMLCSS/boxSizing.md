## title: 'What does `* { box-sizing: border-box; }` do?'
# subtitle: What are its advantages?


`* { box-sizing: border-box; }` makes every element on the page use the `box-sizing: border-box` approach for calculating the elements `height` and `width`.

## What's the difference?

By default, elements have `box-sizing: content-box` applied, and only the content size is being accounted for if an element has `height` and `width` specified. `box-sizing: border-box` changes how the `width` and `height` of elements are being calculated, `border` and `padding` are also being included in the calculation. The `height` of an element is now calculated by the content's `height` + vertical `padding` + vertical `border` width. The `width` of an element is now calculated by the content's `width` + horizontal `padding` + horizontal `border` width.

The following table indicates whether the property is included in the element's calculation of height and width when it has the respective `box-sizing`:

| Property  | `box-sizing: content-box` (default) | `box-sizing: border-box` |
| --------- | ----------------------------------- | ------------------------ |
| content   | Yes                                 | Yes                      |
| `padding` | No                                  | Yes                      |
| `border`  | No                                  | Yes                      |
| `margin`  | No                                  | No                       |

## Advantages

Taking into account `padding`s and `border`s as part of the box model resonates better with how designers actually imagine content in grids. This is a much more intuitive way to think about boxes and hence many CSS frameworks set `* { box-sizing: border-box; }` globally, so that all elements use such a box model by default.

## References

- [Box Sizing | CSS-Tricks](https://css-tricks.com/box-sizing/)