# Callbacks

You can pass two scopes of function callbacks in the `window.sx_${type}` objects, on `data` or on `render`.

| Fields | Subfields | Allowed Values | Description |
|-|-|-|-|
| `data` | `fn` | function | Your callback function with two arguments `data` and `facets`, e.g. `myFunction(data, facets)`. Results and facet data will be passed to your callback function whenever the query `input` field is changed. *`facets` argument returns null for autocomplete.
|  | `hide_render` | `false (default)`, `true` | If `false`, the respective widget (`#sx-autocomplete` or `#sx-results` will not render the results provided as `data` to your callback function).
| `render` | `fn` | function | Your callback function without arguments, e.g. `myFunction()`. This is a data-less callback after all results have been rendered. |

Each scope of callback (on `data` and on `render`) will send many events, as each of our widgets will generate results on key input into the widget form. These are not singular callbacks, but will trigger on any changes to search query or facet selection. Be warned!

### Code Example

```javascript
// example callback functions for each Search X scope: autocomplete, results
// these are simple functions that log each data for each respective event

var myCallbacks = {
  autocomplete: {
    data: function (data) {
      // will contain full results payload as typeof array
      console.log('intercept the autocomplete data', data)
    },
    render: function () {
      console.log('after autocomplete rendered')
    }
  },
  results: {
    data: function (data, facets) {
      // will contain full results payload as typeof array
      console.log('intercept the results data', data, facets)
    },
    render: function () {
      console.log('after results have rendered')
    }
  }
};

window.sx_autocomplete = {
  debug: true,
  options: {
    cb: {
      data: {
        fn: myCallbacks.autocomplete.data
      },
      render: {
        fn: myCallbacks.autocomplete.render
      } 
    }
  }
};

window.sx_results = {
  debug: true,
  options: {
    cb: {
      data: {
        fn: myCallbacks.results.data,
        hide_render: true
      },
      render: {
        fn: myCallbacks.results.render
      } 
    }
  }
};
```
