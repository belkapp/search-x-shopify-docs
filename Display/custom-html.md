# Custom Html For Results Items

You can define a custom function to render your own HTML product result tiles. Your function must return a string of HTML.

| Fields | Allowed Values | Description |
|-|-|-|
| `options.display.html` | function | Define a custom function that returns html. This function will receive arguments `(entity, style, imageHtml, priceHtml, quickshopHtml)`. |

| Callback Argument | typeof | Description |
|-|-|-|
| `entity` | `object` | This object will be the Product, Article, Collection, or Page object. |
| `style` | `object` | This object be passed conditionally if `entity` is type Product, and using `show_all_variants` configuration. 
| `imageHtml` | `string` | This string is our image html for `entity` or `style`. You can use this or generate your own. 
| `priceHtml` | `string` | This string is our price html for `entity` or `style`. You can use this or generate your own. We respect selected currency and Shopify's conversion. We are working on supporting Shopify's new country/currency mapping, but their API responses are not yet ready. 
| `quickshopHtml` | `string` | This string is our quickshop button html. You can use this or generate your own. 

Your declared function should return a string of html.

### Code Example

```javascript
function myCustomHtml (entity, style, imageHtml, priceHtml, quickshopHtml) {
  console.log('entity', entity)
  console.log('style', style)
  console.log('imageHtml', imageHtml)
  console.log('priceHtml', priceHtml)
  console.log('quickshopHtml', quickshopHtml)
  // MUST RETURN typeof 'string'
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

## Additional Considerations

### Quick Shop

If you would like to use our existing Quick Shop feature, you must return the contents of the arguments `imageHtml` and `quickShopHtml` in your string. The javascript for our Quick Shop references their html contents, and requires specific attributes in order to function correctly.

Try this to start:

```javascript
function myCustomHtml (entity, style, imageHtml, priceHtml, quickshopHtml) {
  // MUST RETURN typeof 'string'
  return entity.title + imageHtml + quickshopHtml
}

window.sx_autocomplete = {
  options: {
    display: {
      html: myCustomHtml
    }
  }
};
```
