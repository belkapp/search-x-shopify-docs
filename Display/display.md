# Display

Below are the display options for the autocomplete and results widgets.

| SX Type | Fields | Allowed Values | Description |
| -- | -- | -- | -- |
| `autocomplete` | `color_theme` | `'light' (default)`, `'dark'` | This will change the icon color if `icon_open` is declared. `dark` renders a white icon, so if your page is white, it will disappear. |
| | `form_open` | `false (default)`, `true` | This will render the autocomplete form open by default, and hide the search icon. |
| | `hide_sold_out` | `true (default)`, `false` | Hide sold out items in autocomplete results. |
| | `position` | `left (default)`, `right` | The autocomplete widget results are absolute positioned left by default to hover over any elements below the results set. |
| `results` | `column_collapse_show` | `false (default)`, `true` | _Desktop Only_ - Show an icon that allows the user to collapse the main facet and navigation column. |
| | `column_collapse_default` | `false (default)`, `true` | _Desktop Only_ - If `column_collapse_show`, default the facet and navigation column to the collapsed state. |
| | `facet_scrolltop` | object | [more info here](facet-scrolltop.md) |
| | `hide_column` | `false (default)`, `true` | _Desktop Only_ - Hide the main filtering column that contains entity scopes (Products, Collections, Articles, Pages) and all facets/filters. |
| | `hide_h1` | `false (default)`, `true` | Hide the dynamically generated `<h2>` tag that reflects the combined search query and facets selected, e.g. `<h1>Shirt : Green : Large: Nike</h1>`. This feature is really great for SEO, so please consider that before turning it off. |
| | `hide_sold_out` | `false (default)`, `true` | Hide sold out items in results. |
| | `hide_style_name` | `false (default)`, `true` | Hide variant style name in results when filtering by color, or when showing all variant colors in results: `show_all_variants`. |
| | `html` | callback | Define a custom function that returns html. This function will receive arguments `(entity, style, imageHtml, priceHtml, quickshopHtml)`. `entity` will be the Product, Article, Collection, or Page object. `style` will show conditionally if `entity` is type Product, and using `show_all_variants` configuration. [Example here >](custom-html.md) |
| | `images_hide` | object | [more info here](images-hide.md) |
| | `layout` | `'left' (default)`, `'right'` | Display facets column on left or right of the page. |
| | `show_all_variants` | `false (default)`, `true` | Show all product variants in results. This shows a single variant by style. |
| | `show_variant_thumbs` | `false (default)`, `true` | Show thubmnail images of remaining variants below main product variant. This is not applicable if `show_all_variants: true`. |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    display: {
      color_theme: 'dark',
      form_open: true
    }
  }
};

window.sx_results = {
  options: {
    display: {
      layout: 'right'
    }
  }
};
```
