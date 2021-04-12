# Custom Html For Results Items

| Fields | Allowed Values | Description |
|-|-|-|
| `options.display.html` | callback | Define a custom function that returns html. This callback will send arguments `(entity, style, imageHtml, priceHtml, quickshopHtml)`. |

| Callback Argument | typeof | Description |
|-|-|
| `entity` | `object` | This object will be the Product, Article, Collection, or Page object. |
| `style` | `object` | This object be passed conditionally if `entity` is type Product, and using `show_all_variants` configuration. |
| `imageHtml` | `string` | This string is our image html for `entity` or `style`. You can use this or generate your own. |
| `priceHtml` | `string` | This string is our price html for `entity` or `style`. You can use this or generate your own. We respect selected currency and Shopify's conversion. We are working on supporting Shopify's new country/currency mapping, but their API responses are not yet ready. |
| `quickshopHtml` | `string` | This string is our quickshop button html. You can use this or generate your own. |

### Code Example

```javascript
function myCustomHtml (entity, style, imageHtml, priceHtml, quickshopHtml) {
  console.log('entity', entity)
  console.log('style', style)
  console.log('imageHtml', imageHtml)
  console.log('priceHtml', priceHtml)
  console.log('quickshopHtml', quickshopHtml)
  return 'foobar'
}

window.sx_autocomplete = {
  options: {
    display: {
      html: myCustomHtml
    }
  }
};
```
