# Google Analytics

If Google Analytics is loaded on your page, we will fire GA events by default. We support both Universal Analytics and the new GA4/gtag event conventions.

### Options

| Field | Allowed Values |
|-|-|
| `ga` | `true (default)`, `false` |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    ga: 'false'
  }
};

window.sx_results = {
  options: {
    ga: 'false'
  }
};
```

### GA Event Definitions

Look for these events in GA.

| Category | Action | Label | Description |
|-|-|-|-|
| `SX-Query` | `Change` | `Query: {{user query}}` | User initiates a search query |
| `SX-Facet` | `Select` | `Facet Selected: {{facet value}}` | User clicks a facet / filter |
| `SX-Sort` | `Change` | `Sort Changed: {{sort value}}` | User changes results sort |
| `SX-Page` | `Select` | `Page Changed: {{page number}}` | User goes to next page of results, or requests a page of results directly |
