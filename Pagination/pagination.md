# Pagination

Below are the display options for pagination inside the search results widgets.

| SX Type | Field | Allowed Values  | Description |
| - | - | - | - |
| `sx_results` | `pagination` | `auto (default)`, `paged` | Either auto-scroll or paged pagination. Autoscroll will automatically save the page position in the result set; if the page is reloaded the visitor will start at the beginning of that page of results. |

### Code Example

```javascript
window.sx_results = {
  options: {
    pagination: 'paged'
  }
};
```
