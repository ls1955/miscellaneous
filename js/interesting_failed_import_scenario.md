Encountered this interesting scenario when working on a React Native project.

Reproduce:
```js
import {FOO} from "non/existent/path;
import {BAR} from "legit/path";

// As FOO isn't being use yet, there is no error on import with non/existent/path
BAR // undefined (fail to import BAR from legit/path)
```

Before recognizing the actual cause, here is the work around that author used in order to use BAR.

Hack:
```js
import {FOO} from "non/existent/path;
import {BAR} from "legit/path";

console.log(BAR) // HACK. Somehow console.log BAR beforehand make BAR available again.
BAR // Whatever BAR is.
```
