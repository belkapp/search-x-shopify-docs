# Scopes Display - Hide Images

Use this config if you would like to hide images and render just a simple list for search results.

| Main Field | Allowed SubFields | Allowed Values | Description |
|-|-|-|-|
| `display.images_off` | `products`, `collections`, `articles`, `pages` | `true, false (default)` | Hide images in search results and render just a simple list of entity titles. |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    display: {
      images_off: {
        collections: true
      }
    }
  }
};
```
