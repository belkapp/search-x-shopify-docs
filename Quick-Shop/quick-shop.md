# Quickshop

Below are the Quick Shop options for search results. Quick Shop allows the visitor to hover over a product and open a more detailed overlay with product information, price, and add-to-cart.

| SX Type | Field | Allowed SubFields | Allowed Values | Description |
| -- | -- | -- | -- | -- |
| `sx_results` | `quickshop` | `cb_atc` | `function (cartData) {}` | ADD TO CART CALLBACK — Add a callback function for add to cart. Your callback will recieve a single argument `(cartData)` type object. This callback will be fired every time a product is added to cart from the Quick Shop overlay. |
| | | `cb_render` | `function (product) {}` | RENDER CALLBACK — Add a callback function that fires after the quickshop overlay has rendered. Your callback will recieve a single argument `(product)` type object. |
| | | `cb_waitlist` | `function (product, variantId) {}` | WAITLIST CALLBACK — Add a callback function for waitlist if product size variant is sold out. Your callback will recieve arguments `(product, variantId)`. This callback will be fired every time a sold out size is clicked inside of the quickshop widget. You may want to use this for something like a 'back in stock' email signup form. |
| | | `show` | `false (default)`, `true` | Show 'quick shop' option in products search results. |
| | | `simple_labels` | `false (default)`, `true` | The default view for color variants in the quick shop overlay is image thumbnails. Set `quickshop.simple_labels` to `true` to show show variant colors as simple text labels. |

### Code Example

```javascript
window.sx_results = {
  options: {
    quickshop: {
      show: true,
      simple_labels: true
    }
  }
};
```
