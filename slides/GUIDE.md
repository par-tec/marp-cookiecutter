# Marp slide authoring notes

## Background images

Do **not** use CSS `url()` in embedded `<style>` blocks for local files.
The Marp VS Code preview blocks local paths in CSS; `url()` silently produces nothing.

Use the `_backgroundImage` local directive instead — Marp resolves its path relative to the markdown file, same as `![bg]()`:

```markdown
<!--
_class: cover
_backgroundImage: "url('assets/img/cover.svg')"
-->
```

Alternatively, keep `![bg](assets/img/cover.svg)` in the slide body (original Marp syntax).

## Footer

### Global footer (all slides)

Set a text footer in the front matter:

```yaml
footer: "Author | Conference Year"
```

To use an image as the footer, place a global directive **after** the front matter (before the first `---` slide separator), outside `<style>`:

```markdown
<!-- footer: ![w:150](assets/img/logo.svg) -->
```

Then reposition it with CSS (the default position comes from the active theme):

```css
footer {
  left: auto; right: auto; top: auto; bottom: auto; /* unset theme defaults */
  right: 20px;
  bottom: 20px;
}
```

### Per-slide footer override

```markdown
<!-- _footer: "custom text for this slide only" -->
```

Use `<!-- _footer: "" -->` to hide the footer on a specific slide (e.g. the cover).

### Logo pinned to corner (alternative: pseudo-element)

Using `footer` ties up the footer directive for other use.
`section::before` keeps the logo independent:

```css
section::before {
  content: url('assets/img/logo.svg');
  width: 150px;
  position: absolute;
  right: 20px;
  bottom: 10px;
}
```

For PNG (SVG `content:url()` resizes; PNG does not):

```css
section::before {
  content: '';
  background: url('assets/img/logo.png') no-repeat right bottom / contain;
  width: 150px;
  height: 50px;
  position: absolute;
  right: 20px;
  bottom: 10px;
}
```

## Page number position

Move paginate number to bottom-left:

```yaml
paginate: true
```

```css
section::after {
  right: auto;
  left: 30px;
}
```

## References

- [marp-team discussion #200](https://github.com/orgs/marp-team/discussions/200) — footer logo placement methods
