
There is no solution yet.

Would you like to [contribute to the solution](https://github.com/BFEdev/BFE.dev-solutions/blob/main/react/usetoggle_en.md)? [Contribute guideline](https://github.com/BFEdev/BFE.dev-solutions#how-to-contribute)

import React, {useState, useCallback} from 'react'

export function useToggle(on: boolean): [boolean, () => void] {
  // your code here
  const [value, setValue] = useState(!!on)

  const toggle = useCallback(() => {
    setValue(x => !x)
  }, [])

  return [value, toggle]
}


// if you want to try your code on the right panel
// remember to export App() component like below

export function App() {
  const [value, toggle] = useToggle(false)

  return (
    <>
      <p>
        Value is <code>{value.toString()}</code>
      </p>

      <button onClick={toggle}>toggle</button>
    </>
  )
}
