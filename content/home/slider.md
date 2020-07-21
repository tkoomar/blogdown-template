+++
# Slider widget.
widget = "slider"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 1  # Order that this section will appear.

# Slide interval.
# Use `false` to disable animation or enter a time in ms, e.g. `5000` (5s).
interval = 5000

# Slide height (optional).
# E.g. `500px` for 500 pixels or `calc(100vh - 70px)` for full screen.
height = ""

# Slides.
# Duplicate an `[[item]]` block to add more slides.
[[item]]
  title = "Hello"
  content = "Would you like to contact me?"
  align = "center"  # Choose `center`, `left`, or `right`.

  # Overlay a color or image (optional).
  #   Deactivate an option by commenting out the line, prefixing it with `#`.
  overlay_color = "#FFFFFF"  # An HTML color value.
  overlay_img = "headers/pexels-02.jpg"  # Image path relative to your `static/img/` folder.
  overlay_filter = 0.5  # Darken the image. Value in range 0-1.

  # Call to action button (optional).
  #   Activate the button by specifying a URL and button label below.
  #   Deactivate by commenting out parameters, prefixing lines with `#`.
  cta_label = "Click Here"
  cta_url = "#contact"

[[item]]
  title = "Left"
  content = ":smile:"
  align = "left"

  overlay_color = "#FFFFFF"  # An HTML color value.
  overlay_img = "headers/pexels-01.jpg"  # Image path relative to your `static/img/` folder.
  overlay_filter = 0.25  # Darken the image. Value in range 0-1.

[[item]]
  title = "Right"
  content = ":car:"
  align = "right"

  overlay_color = "#FFFFFF"  # An HTML color value.
  overlay_img = "headers/pexels-03.jpg"  # Image path relative to your `static/img/` folder.
  overlay_filter = 0.25  # Darken the image. Value in range 0-1.
+++
