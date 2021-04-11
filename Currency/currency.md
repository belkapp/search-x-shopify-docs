# Currency

Show a currency selection menu on a results pages. This menu will default to your default currency in Shopify, and will be populated with your pre-approved Shopify currencies.

Once the user makes a selection to change the currency, that preference will then update the autocomplete results prices on the next search, as well as being cookied for future sessions of that user.

| Fields | Allowed Values | Description |
|-|-|-|
| `default` | string | Set default currency. This would override your default currency from Shopify. This may be useful if you already use a select menu to change currencies, or change currency based on location. |
| `show_menu` | `false (default)`, `true` | Show currency selection menu on results page. |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    currency: {
      default: 'EUR',
      show_menu: true
    }
  }
};
```
