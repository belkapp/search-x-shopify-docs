# Facet/Filter Groups Sorting

Sort facets/filter groups by providing an array. This can also apply to custom Tag Groups. In the case of Tag Groups, use the label of the group in lowercase, e.g. `patterns`. For all standard facets, you must use the field names [here](facets.md#facet-fields).

### Code Example

```javascript
window.sx_results = {
  options: {
    facets_sort: ['option_0', 'option_1', 'patterns'] // LOWEST TO HIGHEST PRIORITY, LOWERCASE
  }
};
```
