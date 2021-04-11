# Field Boosting

You may boost up to three values for a single field type. For example, prioritize results that contain values `['men', 'bags']` for the field `product_type`. 

| SX Type | Field | Allowed SubFields | Allowed Values | Description |
|-|-|-|-|-|
| `sx_autocomplete` | `f_boost` | `field` | `'product_type'`, `'tags'`, `'title'`, `'vendor'` | Specify the field on which to apply boost. |
| | | `value` | string or array | Case insensitive matching.<br><br>If result items that contain the field specified above, and that field contains the specified values, matching items will be sent to the top of the entire result set. The match is explicit, not 'contains'. For example, the match is `value === 'men'`, not `value.indexOf('men') > -1`.<br><br>For example, prioritize results that contain the field `product_type` where its value equals either `['men', 'bags']`. Items that where value equals `men` will be boosted to the top, then items where the value equals `bags` will be boosted above all others.<br><br>If using array here, array can contain maximum of 3 values. |
| `sx_results` | `f_boost` | `field` | `'author'`, `'product_type'`, `'option_0'`, `'option_1'`, `'option_2'`, `'tags'`, `'title'`, `'vendor'` | Specify the field on which to apply boost. |
| | | `value` | string or array | Case insensitive matching.<br><br>If result items that contain the field specified above, and that field contains the specified values, matching items will be sent to the top of the entire result set. The match is explicit, not 'contains'. For example, the match is `value === 'men'`, not `value.indexOf('men') > -1`.<br><br>For example, prioritize results that contain the field `product_type` where its value equals either `['men', 'bags']`. Items that where value equals `men` will be boosted to the top, then items where the value equals `bags` will be boosted above all others.<br><br>If using array here, array can contain maximum of 3 values. |

### Code Example

```javascript
window.sx_results = {
  options: {
    f_boost: {
      field: 'product_type',
      value: ['men', 'bags'] // LOWEST TO HIGHEST PRIORITY
    }
  }
};
```
