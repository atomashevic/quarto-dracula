# Dracula Themme for Quarto HTML Documents

This is a simple scss file that can be used to apply the [Dracula](https://draculatheme.com/) theme to Quarto HTML documents.

I used the basic colors from the Dracula theme and applied them to the Quarto HTML theme. Also, math font is increased for better readability.

Obviously, it looks best when paired with Dracula syntax highlighting for code blocks which is already implemented in Quarto.

You can see the **live example [here](https://atomasevic.com/dracula-example)**.

## Usage

To use this theme, simply copy the [dracula.scss](dracula.scss) file to your project and include it in your Quarto configuration file.

```yaml
project:
  type: website

website:
  title: "Website Title"

format:
  html:
    theme: dracula.scss
    highlight-style: dracula
```

## Issues

### Callouts are not working

This piece of code is not working. This is solvable, probably answers can be found here: https://github.com/quarto-dev/quarto-cli/discussions/4755


```scss
// Callout Styles
.callout {
  padding: 1em;
  margin: 1em 0;
  border-left: 5px solid $secondary !important;
  background-color: lighten($body-bg, 5%) !important;
}

.callout-note.callout {
  border-left-color: $callout-note-border !important;
  background-color: $callout-note-bg !important;
}

.callout-warning.callout {
  border-left-color: $callout-warning-border !important;
  background-color: $callout-warning-bg !important;
}

.callout-important.callout {
  border-left-color: $callout-important-border !important;
  background-color: $callout-important-bg !important;
}

.callout-tip.callout {
  border-left-color: $callout-tip-border !important;
  background-color: $callout-tip-bg !important;
}

.callout-caution.callout {
  border-left-color: $callout-caution-border !important;
  background-color: $callout-caution-bg !important;
}
```

If you can fix this, PRs are welcome!

### Math font size

If you find the math font size too big, you can adjust it by changing these lines in the `dracula.scss` file:

```scss

// Math Expressions
.math {
  font-size: 120%; // Change this value to adjust the math font size in math blocks
}

// Increase font size for inline math in paragraphs and lists
p .math, li .math, blockquote .math {
  font-size: 110%; // Change this value to adjust the inline math font size
}
```
