```
a(1) - b(10) - d(1)
  \      \
   c(10)  e(1)
```

```ts
import { graphSequencer } from "@pnpm/deps.graph-sequencer"
console.log(graphSequencer(
  new Map([
    ["a", ["b", "c"]],
    ["b", ["d", "e"]],
    ["c", []],
    ["d", []],
    ["e", []],

  ],), ["a", "b", "c", "d", "e"]
))
```

```js
{
  safe: true,
  chunks: [ [ 'c', 'd', 'e' ], [ 'b' ], [ 'a' ] ],
  cycles: []
}
```