# Facets / Filters

Facets can:
- be hidden
- have their labels changed
- be filtered in, or filtered out, using basic matching or advanced regex

Facet options are only applicable on the `window.sx_results` object.

### Facet Fields

| Facet Field | Applicable To | Description |
|-|-|-|
| `author` | `articles` | Authors of articles. |
| `blog_list` | `articles` | Blogs in which articles have membership. |
| `collections` | `products` | Collections in which products have membership. |
| `option_0` | `products` | First variant option on product. |
| `option_1` | `products` | Second variant option on product. |
| `option_2` | `products` | Third variant option on product. |
| `product_type` | `products` | Product Type on product. |
| `tags` | `articles`, `products` | Third variant option on product. |
| `vendor` | `products` | Vendor on product. |

You can sort facet fields like [here](facets_sort.md).

### Facet Field Options

The following options are applicable to all facet fields. See the code example further down.

| Option Field | Allowed Values | Description |
|-|-|-|
| `colors`| `false (default)`, `true` | Show matched color thumbnails for this facet. This would be applicable to either variant option `option_0`, `option_1`, or `option_2`. It depends to which variant option position you use for color. |
| `hide`| `false (default)`, `true` | Hide the facet. |
| `label`| string | Change the label value, e.g. `window.sx_results.facets.authors.label = 'Writers'` will change the facet `Authors` to `Writers` |
| `filter_exclude`| string | Exclude any items that match string value. Either treated as 'contains' or regex as described below. |
| `filter_include`| string | Exclude any items that match string value. Either treated as 'contains' or regex as described below. |

### Matching Options for `filter_exclude`, `filter_include`

The following options are applicable to all facet fields. See the code example further down.

| Match Type | Match String|
|-|-|
| Match as 'contains' | If value provided is string, this will match as case insensitive 'string contains x'. For example, filter every item that contains the text `imported_at:`. |
| Match using regex | You may include a valid regex string for more specific matching patterns. Do not include the regex wrapper `//ig`. You must double escape forward slashes.  Our regex options are case insensitive `i`, and NOT global `g`.<br><br>For example, match sizes `(^[xs|s|m|l|xl]$)|extra|small|medium|large|[0-9]`<br><br>or match items that start with a dollar sign or a number `\\$|[0-9]`. Notice the double escaping here. We must double escape because we lose one escape character when passing around the object 🤷‍♂️ |

*[https://regexr.com/](https://regexr.com/) is a fantastic tool to test your regex.


### Code Example

```javascript
window.sx_results = {
  options: {
    facets: {
      collections: {
        label: 'Categories'
      },
      option_0: {
        label: 'Colors',
        filter_exclude: '\\$|[0-9]'
      },
      option_1: {
        label: 'Sizes',
        filter_include: '(^[xs|s|m|l|xl]$)|extra|small|medium|large|[0-9]'
      },
      option_2: {
        hide: 'true'
      },
      product_type: {
        label: 'Product Type'
      },
      vendor: {
        label: 'Brands'
      },
      tags: {
        filter_exclude: '^[0-9]+'
      }
    }
  }
};
```
