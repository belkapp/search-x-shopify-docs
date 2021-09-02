# Scopes Display - Image Size

Use this config to change image sizes for mobile and desktop, as well as changing the breakpoint between mobile and desktop image sizing (default is 900).

| Main Field | Allowed SubFields | Allowed Values | Description |
|-|-|-|-|
| `display.image_size` | `mobile` | string following convention `600x600` | For example, to change mobile images to 600px by 600px, use `600x600`. For 1200px by 1200px, use `1200x1200`.  |
| | `desktop` | string following convention `600x600` | For example, to change desktop images to 800px by 800px, use `800x800`. For 2000px by 2000px, use `2000x2000`.  |
| | `bp` | number | For example, to override mobile breakpoint to 700, use `700`.  |

### Code Example

```javascript
window.sx_autocomplete = {
  options: {
    display: {
      image_size: {
        mobile: '300x300',
        desktop: '2000x2000',
        bp: 700
      }
    }
  }
};
```
