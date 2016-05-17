# how to open source

**follow the modules**

## open source is personal

from my personal experience, open source is about:

- your internal motivation to develop
- your relationships with other developers

## find your motivation

- what gives your energy?
- what depletes your energy?

do more of what gives you energy and less of what depletes your energy.

## the mad science cycle

> if you see something that needs doing, it's your job

1. find a small iterative step in the direction towards a goal
1. work on this small step and publish everything along the way
1. share with other developer friends, get feedback on results
1. rinse and repeat

## follow who you want to be on GitHub

- see what repos they create
- see what repos they star
- follow progress on repos you enjoy
- dive in where you think you can contribute

## why small modules?

> tl;dr You make small focused modules for reusability and to make it possible to build larger more advanced things that are easier to reason about.
> 
> People get way too easily caught up in the LOC (Lines Of Code). LOC is pretty much irrelevant. It doesn't matter if the module is one line or hundreds. It's all about containing complexity. Think of node modules as lego blocks. You don't necessarily care about the details of how it's made. All you need to know is how to use the lego blocks to build your lego castle. By making small focused modules you can easily build large complex systems without having to know every single detail of how everything works. Our short term memory is finite. In addition, by having these modules as modules other people can reuse them and when a module is improved or a bug is fixed, every consumer benefits.
> 
> Imagine if PC manufacturers all made their own CPUs. Most would do it badly. The computer would be more expensive and we would have slower innovation. Instead most use Intel, ARM, etc.
> 
> This would not be possible if it weren't for how npm works. The beauty of being able to use nested dependencies means I don't have to care what dependencies a dependency I use have. That's powerful.
> 
> Some years ago. Before Node.js and npm. I had a large database of code snippets I used to copy-paste into projects when I needed it. They were small utilities that sometimes came in handy. npm is now my snippet database. Why copy-paste when you can `require` it and with the benefit of having a clear intent. Fixing a bug in a snippet means updating one module instead of manually fixing all the instances where the snippet is used.
> 
> For example. I have this module [negative-zero](https://github.com/sindresorhus/negative-zero). Its job is to tell me if a number is `-0`. Normally you wouldn't have to care about this, but it could happen. How do you figure out if a number is `-0`. Well easy `x === 0 && 1 / x === -Infinity`. Or is it? Do you really want to have to know how and why this works? I would rather require `negative-zero` and be productive on other things.
> 
> Another example. [Chalk](https://github.com/chalk/chalk) is one of the most popular modules on npm. What you might not realize is that it's actually a [collection of modules](https://github.com/chalk/chalk/blob/d7537f37df874619511994f1debf2ec6dbacaa3c/package.json#L48-L52). It depends on a module for [detecting if the terminal supports color](https://github.com/chalk/supports-color), for [getting the ansi escape codes](https://github.com/chalk/ansi-styles), etc. All of this could have been just embedded in the main module, and it probably *is* in many cases. But that would mean anyone else wanting to create an alternative terminal string styling module would have to reinvent the wheel on everything. By having these supporting modules, people can easily benefit from our work in Chalk and maybe even help improve Chalk indirectly by improving one of the dependencies.
> 
> Yet another example. I have this module [user-home](https://github.com/sindresorhus/user-home) which get's the user's home directory. You might think it would be simpler to just do `process.platform === 'win32' ? process.env.USERPROFILE : process.env.HOME`. And most do this. But first, why require everyone to know how to get the home directory? Why not use a \"lego block\"? What you also might not realize is that this check is incomplete. On Windows you should also check `process.env.HOMEDRIVE + process.env.HOMEPATH` and you might also want to do [additional checks](https://github.com/sindresorhus/os-homedir/blob/7e39e2e049de404f06233fa617ecf46fed997a78/index.js). Lego blocks.
> 
> Do you make your own shoes? No, you buy them in a store. Most don't care how the shoe is made. Just how good it fits.
> 
> I want programming to be easier. Making it easier to build durable systems. And the way forward in my point of view is definitely not reinventing everything and everyone making the same stupid mistakes over and over.

@sindresorhus on ["one-line node modules"](https://github.com/sindresorhus/ama/issues/10#issuecomment-117766328)

## how to write small modules

you're already writing modules, they are just trapped in your code, waiting to be let free.

> As much as possible, I try to build large-scale projects using lots of tiny modules so I just repeat this process whenever I need some reusable component that doesn't yet exist in quite the form I need it to exist. As more modules are published to npm I expect I won't need to write so many modules but there will always be room for new stuff.
>
> When applications are done well, they are just the really application-specific, brackish residue that can't be so easily abstracted away. All the nice, reusable components sublimate away onto github and npm where everybody can collaborate to advance the commons.

- @substack on ["how i write modules"](http://substack.net/how_I_write_modules)

> Most software exists in the `lib/` folder. Most programmers work on one repo and put all their hard work into `lib/`. The appearance of productivity that you see amongst people like @sindresorhus is achieved simply through taking the small extra effort up front to document modular components, create repos for them, and publish them to npm. In the long term this strategy saves time as it deduplicates work across projects.

- @maxogden as [a comment to `sindresorhus/ama#13`](https://github.com/sindresorhus/ama/issues/13#issuecomment-117788546)

## frameworks

"frameworks" (using the term loosely) is a formal collections of modules, often sponsored by a company.

- [nodejs](https://github.com/nodejs/node)
- [feathersjs](https://github.com/feathersjs)
- [reactjs](https://github.com/reactjs)

## core politics

> If software ecosystems are like economies then core libraries are at best government bureaucracies and at worst nationalized state corporations. That is, modules in the core distribution get an unfair advantage over the libraries in userspace by virtue of availability and prominance. Worse still, because these modules are all maintained in the core project, contributing, experimenting, and iterating is much harder than with a typical library on npm.

@substack on ["node aesthetic: batteries not included"](https://github.com/substack/blog/blob/master/node_aesthetic.markdown#batteries-not-included)

> the stdlib is a political problem, it privileges the people who want to do it that way.

> get things like this https://github.com/nodejs/node/pull/5020#issuecomment-177978212

@dominictarr on ["SACRIFICE CORE ON THE MODULARITY ALTAR"](https://twitter.com/dominictarr/status/714753766990430208)

## module ecosystems

module ecosystems are informal collections of modules under a common umbrella.

- [stack.gl/packages](http://stack.gl/packages)
- [scijs.net/packages](http://scijs.net/packages/)
- [level](https://github.com/level)
- [webtorrent#modules](https://github.com/feross/webtorrent#modules)
- [webcoin#modules](https://github.com/mappum/webcoin#modules)
- [nodeschool#workshoppers](http://nodeschool.io/#workshoppers)
- [ssbc](https://github.com/ssbc)
- [stackcss](https://github.com/stackss)
- [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs)
- [awesome-mad-science](https://github.com/feross/awesome-mad-science)

> An argument I often hear in favor of frameworks is that it helps a big team rally around some common tools that everybody is familiar with. This is true, but I often observe the same benefits collaborating with people who use some of my favorite low-level stream modules like `through` and `duplexer` or when authors use interfaces from node core like .pipe().

> If your framework melts away into an informal collection of modules that happen to work well together but can be easily repurposed by people who don't use the framework, then you have built something very sublime.

@substack on ["many things"](http://substack.net/many_things)

## [OPEN open source](http://openopensource.org/)

> Individuals making significant and valuable contributions are given commit-access to the project to contribute as they see fit. This project is more like an open wiki than a standard guarded open source project.

## how to suggest a feature

be actionable, clear, and kind! :)

good examples:

- [substack/node-mkdirp#86](https://github.com/substack/node-mkdirp/issues/86)
- [mmckegg/loop-drop-app#187](https://github.com/mmckegg/loop-drop-app/issues/187)

bad examples:

- [cobudget/cobudget-ui](https://github.com/cobudget/cobudget-ui/issues/272)
- [mmckegg/loop-drop-app#186](https://github.com/mmckegg/loop-drop-app/issues/186)

## how to report a bug

1. expected behavior
1. actual behavior
1. detailed steps to reproduce
1. version / environment details

good examples:

- [stackcss/sheetify#69](https://github.com/stackcss/sheetify/issues/69)

bad examples:


## how to submit a pull request

provide test cases that support your code changes.

good examples:

- [holodex/csv-formatter#4](https://github.com/holodex/csv-formatter/pull/4)

bad examples:



## open source consumerism

> A major problem open source developers today face is [open source consumerism](https://the-pastry-box-project.net/charlie-robbins/2014-January-5):
>
> > A point at which one stops hearing "I love your project!" and "thank you for your hard work" and starts to hear "what have you done for me lately?" or "is this project abandoned?"
>
> As a project moves from scratching a personal itch to maintenance for others, a shift occurs. No longer is the project driven by your own desires, it's driven by the desires of others. Working on a pet project is having a hobby, working on a project for others is being an unpaid intern.
>
> > Each support request, each feature request, each complaint, is an issue — as a product becomes more popular, the costs of maintenance increase exponentially; and it's not something that can be solved by pumping more contributors into the system, as there is still operating and organisation costs, and there is always still rent and bills to pay.
>
> > -- @balupton in [bevry/meta#16](https://github.com/bevry/meta/issues/16#issuecomment-55358662)

- @ahdinosaur in ["Workers of Open Source, Unite!"](https://blog.dinosaur.is/workers-of-open-source-unite/)

## open source burnout

- [babel author burns out](https://medium.com/@sebmck/2015-in-review-51ac7035e272#089f)
- [isaacs/github#167](https://github.com/isaacs/github/issues/167)

## [stigmergy](https://en.wikipedia.org/wiki/Stigmergy)

join the swarm!

## other resources

- [@github on "Contributing to Open Source"](https://guides.github.com/activities/contributing-to-open-source/)
- ["Why Should I Care What Color The Bikeshed Is?"](http://bikeshed.com/)
- [Producing Open Source Software](http://producingoss.com/)
- [@rms on Free Software](https://www.gnu.org/events/rms-nyu-2001-transcript.html)
- [The Cathedral and the Bazaar](http://www.catb.org/~esr/writings/cathedral-bazaar/)
- [Free Software, Free People](https://www.youtube.com/watch?v=A3dimvwrnO8)
