# Reviews

We support the following review apps: **Shopify Product Reviews**, **Loox**, **Yotpo**, **JudgeMe**, and **Stamped**.

### Options

Specifying any of the review apps below will automatically show review star rating in autocomplete and search results.

| Field | Allowed Values | Description |
|-|-|-|
| `reviews` | `spr` | Shopify Product Reviews |
| | `loox` | Loox |
| | `yotpo` | Yotpo |
| | `judgeme` | JudgeMe |
| | `stamped` | Stamped |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    reviews: 'spr'
  }
};

window.sx_results = {
  options: {
    reviews: 'spr'
  }
};
```
