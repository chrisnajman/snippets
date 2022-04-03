# Snippets

## React component: output ul tags around list items only when there are items in the array.

```jsx
import React from "react"

const sportsArray = ["Tennis", "Football", "Basketball", "Swimming", "Chess"]

const SportsList = () => {
  return (
    <div>
      {sportsArray && sportsArray.length > 0 && (
        <ul>
          {sportsArray.map((sport, i) => {
            return <li key={i}>{sport}</li>
          })}
        </ul>
      )}
    </div>
  )
}

export default SportsList
```

Source: [Stack Overflow question - Output ul tags conditionally in JSX?](https://stackoverflow.com/questions/71704452/output-ul-tags-conditionally-in-jsx/71704495?noredirect=1#comment126724402_71704495).

---

## HTML: Adding semantic meaning to the `<section>` element.

The `<section>` element on its own carries no semantic meaning. For it to have one, either `aria-labelledby` or `aria-label` is required:

### a) `aria-labelledby`

In this case, we associate `aria-labelledby` with the `id` of the heading (**every section element should have a heading**).

```html
<section aria-labelledby="section-1">
  <h2 id="section-1">Section 1</h2>
  <p>This is section 1</p>
</section>
```

### b) `aria-label`

If we want the section to have a label independent of any or no `id` on the heading, we use `aria-label`:

```html
<section aria-label="Section 2">
  <h2>This is the section 2 title</h2>
  <p>This is section 1</p>
</section>
```

Following either of the two techniques will allow assistive technologies to navigate towards these labelled sections (which will be presented to the user as a _list of regions_).

#### Notes:

1. In example a) the section will be identified with the value of the heading element: "Section 1".
2. In example b) the section will be identified with the value of `aria-label`: "Section 2".
3. If the content of the `<section>` is not sufficiently important to be included in a _list of regions_, a simple `<div>` element should be used instead.

Source: [Kevin Powell, YouTube - HTML section elements are a lie (sort of)](https://youtu.be/ULdkpU51hTQ).

---
