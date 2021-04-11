# Scope Labels

Below are the display options scope labels inside of the search results widgets.

| SX Type | Field | Allowed Subfields | Allowed Attributes | Allowed Values | Description |
| - | - | - | - | - | - |
| `sx_results` | `scope_labels` | `products`, `collections`, `articles`, `pages` | `label` | string | Change the scope labels inside of the search results widgets. For example, change `products` which defaults to a label of "Products" to "Stuff". |
| | | | `hide` | `true`, `false (default)` | Hide main navigation scope in search results. E.g. hide "Articles" scope from the main navigation. |

### Code Example

```javascript
window.sx_results = {
  options: {
    scope_labels: {
      products: {
        label: 'Stuff'
      },
      articles: {
        hide: true
      }
    }
  }
};
```
