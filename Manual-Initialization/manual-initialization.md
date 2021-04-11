# Manual Initialization

To initialize either widget manually, declare `options.init_manual` in the options configuration object.

Then you will call `sxinit('autocomplete')` or `sxinit('results')` in order to initialize your desired widget.

| Fields | Allowed Values |
|-|-|
| `init_manual` | `false (default)`, `true` |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    init_manual: true
  }
};

window.sx_results = {
  options: {
    init_manual: true
  }
};

setTimeout(function () {
  // WAIT 5 SECONDS AND INTIALIZE AUTOCOMPLETE
  sxinit('autocomplete')
}, 5000)

setTimeout(function () {
  // WAIT 10 SECONDS AND INTIALIZE RESULTS
  sxinit('results')
}, 10000)
```
