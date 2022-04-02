# Snippets

1. React component: output ul tags around list items only when there are items in the array.

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

Source: [Stack Overflow question - Output ul tags conditionally in JSX?](https://stackoverflow.com/questions/71704452/output-ul-tags-conditionally-in-jsx/71704495?noredirect=1#comment126724402_71704495), answered by [Praveen Kumar Purushothaman](https://stackoverflow.com/users/462627/praveen-kumar-purushothaman)

---
