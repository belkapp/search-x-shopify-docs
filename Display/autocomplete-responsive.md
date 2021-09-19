# Autocomplete - Responsive Display

There may be times where your theme will require two autocomplete divs `<div id="sx-autocomplete>` for different mobile and desktop views. This occurs when your theme uses two different parts of code for the different views.

You may see something in your liquid code like:

```
<header>
  <div class="header-mobile">
    // MOBILE HEADER CODE
  </div>
  <div class="header-desktop>
    // DESKTOP HEADER CODE
  </div>
</header>
```

This can present problems with Search X getting confused on which view is active.

To solve this issue we add the `data-view` property to differentiate between the two different views like below. Our default breakpoint is 900px.

```
<header>
  <div class="header-mobile">
    // MOBILE HEADER CODE
    <div id="sx-autocomplete" data-view="mobile">
  </div>
  <div class="header-desktop>
    // DESKTOP HEADER CODE
    <div id="sx-autocomplete" data-view="desktop">
  </div>
</header>
```
