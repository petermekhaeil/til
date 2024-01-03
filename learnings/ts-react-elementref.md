# TypeScript: ElementRef for React.useRef

You can extract the type from a `useRef` hook using `ElementRef`:

```tsx
import { useRef, ElementRef } from "react";
 
const Component = () => {
  const audioRef = useRef<ElementRef<"audio">>(null);
//       ^? React.RefObject<HTMLAudioElement>

  return <audio ref={audioRef}>Hello</audio>;
};
```

Read [Matt Pocock's Strongly Type useRef with ElementRef](https://www.totaltypescript.com/strongly-type-useref-with-elementref).
