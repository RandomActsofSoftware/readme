# cljctools

cljctools is a namespace for solving problems freely, for the purpose of value only.    
So it is and will be non-commercial, non-monetized by design.   
Open source.  
It's just tools. But f-ing best ones, made with heart.
All members are owners - so please don't mess up.   
Secure, because members have forks. It's just people.   

## rationale

- cljc stands for clojure common, meaning it is runtime-less (can run on jvm, browser, nodejs ...)
- when buidlding a system for users, you end up having abstractions(libraries, spec, protocols,data generation), that need to be run both on the server and on the client
- and even having javascript, typescript - with their catastrophic flaw of having no namespaces - you still appreciate how easy it is to create a pacakge(dependency) to be used both on nodejs and in browser
- but this is nothing compared to the reach and brilliant simplicity, human-being-nature of clojure: as of 2020, the most (not even close) powerful tool for programming
- clojure not just gives you everything any other remotely-sane language has, it also allows you to right runtime-less code for both server, nodejs and the browser! It has the most reach
- and gives you things other languages cannot dream of
  - as the most advanced Lisp, it is built from data, data everywhere, no parsing
  - has .edn - an extensible data notation (you can add stuff), and transit - the way to send data efficienly across network and runtimes
  - has immutability
  - is itself built in terms of abstractions (Sequential, Associative ... ), implementatable and extendable
  - has fully-qualified auto-resolved keywords (which is the key for designing you project and data - when everything is fully-qualified, no need to hold stuff in your head or for cheats/tricks )
  - has protocols, ability to reify, giving you the most able - as it's just a function - "constructor" in the world
  - has macros and macroexpansion, giving you the most powerful tool to validate/transform anything at compile time - a function call and the whole damn language inside it
  - has .cljc extension and reader conditionals, allowing you to have conditional runtime-specific code in the same file #?(:clj (do this) :cljs (do that))
  - has clojure.spec - the most elegant and simple, yet powerful way to programmatically describe/generate/validate and understand your data once
  - has transducers - no words can be found for what an ahievement that is - a correct way to process a value through steps without creating intermidiate collections, and it's built right into the language  already!
  - has atoms (watchable atomic state), has transients (to do stuff manually for efficiency), has deps.edn to load deps from local dir ot github commit hash and on and on ..
- oh wait, we forgot somehting? somehting most important ? 
- ask yourself a question: why golang has become so used and needed so quickly, and it didn't not even have (does it now?) a sane dependency tool for some time (for those who tried, hello from GOPATH)
  - how did golang became the go-to tool for cloud native and server-side world without having any code base java ecosystem provides,with having to start from sratch?
  - golang delivered kubernetes and docker - the defacto operating systems of the cloud world. How ? that-s right - channels
  - you can handle asynchrony via process and channels (queues), passing channels around is the design purpose of golang, because that is how you build systems
- wait, what? clojure has exaclty that and a bit more, alongside all other features? that's hard to belive, but it is true
  - core.async allows to to design your system as processes and queues (channels), and you wouldn't belive it - core.asycn is a runtime-less abstraction, runs on both jvm, nodejs and in the browser 
  - as the creator of clojure says in his talk on core.async "function chains are poor machines", "good programs should be made out of processes and queues" - could not agree more
- with that in mind
  - cljctools by design build abstractions as processes, with core.async being part of the language (as it is with golang)
  - not every abstraction needs to implemented for every runtime, but it should be defined in terms of protocols and api, with the ability to add another runtime implementation later
  - that is why cljctools libraries will have a meta package, dependecy-less .cljc code (spec, protocols, channel api) so that implementations could share the same abstraction definition
- bigger aspirations
  - mult: a VSCode extension for clojure(script) https://github.com/cljctools/mult/blob/master/docs/design.md#rationale
  - sol: creating a better (simpler) building tool for clojurescript (the name will be "sol" - as in solution, or a day on Mars)
  - nrepl: implementing nrepl anew, with the same protocol at the core, but with the ability to run on nodejs (for self-hosting cljs inside VSCode editor, for full cljs REPL support right in the editor )
  - editor: creating and editor in clojure(script), but only if it can be done better than VSCode
  - origin cluster: an automated volunteer self-forming cloud  https://github.com/DeathStarGame/docs/blob/master/origin-cluster/origin-cluster.md#origin-a-volunteer-automated-cluster
  - opensource database: would it be possible to make a db like dgraph, but with clojure language itself as a query language?
  - ...
- who is all for
  - for users

## why not monetize this project ? you're an idiot

Go buck yourself! This is money free zone, fun zone.

As Jesus says:

> <b>19 “Do not store up for yourselves treasures on earth, where moths and vermin destroy, and where thieves break in and steal. 20 But store up for yourselves treasures in heaven, where moths and vermin do not destroy, and where thieves do not break in and steal. 21 For where your treasure is, there your heart will be also.</b>

> <b>22 “The eye is the lamp of the body. If your eyes are healthy,[c] your whole body will be full of light. 23 But if your eyes are unhealthy,[d] your whole body will be full of darkness. If then the light within you is darkness, how great is that darkness!</b>

> <b>24 “No one can serve two masters. Either you will hate the one and love the other, or you will be devoted to the one and despise the other. You cannot serve both God and money.</b>

source: [NIV Bible, Matthew:6](https://www.biblica.com/bible/niv/matthew/6/)


## links
- mailing list
  - https://groups.google.com/g/cljctools
  - cljctools@googlegroups.com
