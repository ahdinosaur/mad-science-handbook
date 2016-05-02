# functional

> [*functional programming* is a programming paradigm—a style of building the structure and elements of computer programs—that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.](https://en.wikipedia.org/wiki/Functional_programming)

for a great book on functional programming, see [the Structure and Interpretation of Computer Programs (SICP)](https://mitpress.mit.edu/sicp://mitpress.mit.edu/sicp/)

## abstractions

- type: define shape of data
- function: data input -> data output
- effects: data, error, continuation
- stream: data over time

## function

- [Execution in the Kingdom of Nouns](http://steve-yegge.blogspot.co.nz/2006/03/execution-in-kingdom-of-nouns.html)
- [Rich Hickey on Values, Identity, State, Time, and Behavior](http://www.flyingmachinestudios.com/programming/the-unofficial-guide-to-rich-hickeys-brain/

### comparison with "object-oriented programming" (OOP)

> Just a gentle reminder that I took some pains at the last OOPSLA to try to
remind everyone that Smalltalk is not only NOT its syntax or the class
library, it is not even about classes. I'm sorry that I long ago coined the
term "objects" for this topic because it gets many people to focus on the
lesser idea.

> The big idea is "messaging" -- that is what the kernal of Smalltalk/Squeak
is all about (and it's something that was never quite completed in our
Xerox PARC phase). The Japanese have a small word -- ma -- for "that which
is in between" -- perhaps the nearest English equivalent is "interstitial".
The key in making great and growable systems is much more to design how its
modules communicate rather than what their internal properties and
behaviors should be. Think of the internet -- to live, it (a) has to allow
many different kinds of ideas and realizations that are beyond any single
standard and (b) to allow varying degrees of safe interoperability between
these ideas.

> - [Alan Kay, origin of OOP, on "prototypes vs classes"](http://lists.squeakfoundation.org/pipermail/squeak-dev/1998-October/017019.html)

## effects

- [`continuable`](https://github.com/Raynos/continuable)
- [`promise`](https://domenic.me/2012/10/14/youre-missing-the-point-of-promises/)
- [elm architecture / side effects examples](https://medium.com/@yelouafi/elm-architecture-side-effect-examples-with-snabbdom-and-jsx-3732219d9995#.qu4ic8x0z)
- [`tom`](https://github.com/gcanti/tom)
- [don't fear the monad](https://www.youtube.com/watch?v=ZhuHCtR3xq8)

## stream

- [`pull-stream` Design Goals & Rationale](https://github.com/dominictarr/pull-stream#design-goals--rationale)
- [`pull-stream` examples](https://github.com/dominictarr/pull-stream-examples/blob/master/pull.js)
- [@damonoehlman on "Callbacks vs Promises vs Streams"](https://damonoehlman.github.io/posts/2013-07-23-callbacks-vs-promises-vs-streams.html)
- [gist on functional control flow](https://gist.github.com/Integralist/6088405/)
- [issue on callbacks vs events](https://github.com/nodejs/node/issues/188)

## type

