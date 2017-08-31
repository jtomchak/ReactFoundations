##React Notes
* react create app
  * the students are righfully overhelmed at the amount of content in such a short time, there also seems to be an extra level of frustration around the tooling. 
  * introduce it after learning how createElement and jsx work
  * possibly eject right away and explore that it's not black magic that all those tools are avialable to use and costumize
  * the readme at piles of great explanations from preprocessors to adding bootstrap
  * list of [Alternatives](https://github.com/facebookincubator/create-react-app#alternatives)
  * **CONS**
    * magic black box
    * misunderstanding of what react is and isn't 

* react-router
  * client side routing beyond a switch statement
  * i feel like they well need to leverage more robust routing for a group project
  * url parameters
  * dynamic linking
  * hashroutinger and browserAPIhistory
  * similiar concepts to express routing, matching on route and directing action
  * pretty good documentation [DOCS](https://reacttraining.com/react-router/web/example/basic)
  * **CONS**
    * react-router has changed a lot from 1, 2/3, 4
    * additional material to cover is short time

* Flow types
  * a section after Prop validation to introduce flow types
  * good excerise to force students to be explicit about types, even if only for a bit :-)
  * supported by most editors, little extra tooling required
  * easily see the benefits right way 
  * mention alteritives typescipt, tern.js
  * **CONS**
    * this _could_ be a whole day on it's own as a introductory to static types
    * additional tooling seems to add to frustrations for the students. 
    * would be just an introduction, then gotta keep moving forward
    * then enforce flow for the rest of the course ? 

* Higher Order Components
  * I like seeing this in the lessons
  * maybe some of the uses of HOC, first question that I feel would be coming is, "when do I use these", or "why would I use these"
    * Code reuse, logic and bootstrap abstraction (render list item as HOC as an example)
    * Render Highjacking
    * State abstraction and manipulation
    * Props manipulation

* Testing with Jest
  * good reinforcement of lessons, and error feedback
  * we all _should_ be testing
  * **CONS**
    * more content
    * another library to learn(or just start with expect() as minimal)
    * why not karma, jasmine, or other combination
    * again, tooling setup and lift

* Redux Middleware
  * where to even start, so much, maybe too much!
  * maybe just let them know that it's a thing and can offer a lot of convenience
  * possible refactor with something like redux-thunk, for me it's that refactor part that really shows wheather i know something or not. The debugging during this phase is also an oppurtunity to really understand the fundamentals
  * **CONS**
    * of course time is a factor
    * possiblly too much for a introductory
    * it will melt their brains for sure



