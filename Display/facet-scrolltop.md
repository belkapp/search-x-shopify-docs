# Facet/Filter Scroll To Top On Select

Our default behavior is to scroll to the top of the search results container when selecting or deselecting a facet/filter from the main column. You can turn this off. You can also add selectors that will increase the top offset based on the selectors' height. For example, you may have a fixed header, so you can specify the header's container to add to the top scroll offset.

| Main Field | Allowed SubFields | Allowed Values | Description |
|-|-|-|-|
| `display.facet_scrolltop` | `off` | `false (default)`, `true` | Do not scroll to top when selecting or deselecting a facet/filter from the main column. |
|  | `sel` | Array of strings `['.header', '#banner']` | Increase the top offset of the scroll to top to account for overlayed or fixed containers. Use standard CSS selectors. Specify multiple containers as string selectors like `'.header'` in the array. |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    display: {
      facet_scrolltop: {
        off: true,
        sel: ['.header.']
      }
    }
  }
};
```
