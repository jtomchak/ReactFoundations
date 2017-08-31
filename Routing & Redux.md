autoscale: true

# Routing with React
![inline](https://i.ytimg.com/vi/ZurrLqWyRms/maxresdefault.jpg)

---

* react-router
  * client side routing beyond a switch statement
  * url parameters
  * dynamic linking
  * browserAPIhistory
  * similiar concepts to express routing, matching on route and directing action
  * pretty good documentation [DOCS](https://reacttraining.com/react-router/web/example/basic)

---

  * **CONS**
    * react-router has changed a lot from 1, 2/3, 4
    * additional material to cover is short time
    
---

![inline](https://cdn-images-1.medium.com/max/596/1*pMA2Srij3sJ_79xyqvzIrw.png)

---
![inline fill](https://i.ytimg.com/vi/DiLVAXlVYR0/maxresdefault.jpg)

---
## React is the V, don't we need a data model ?
* Flux

>  It complements React's composable view components by utilizing a unidirectional data flow. It's more of a pattern rather than a formal framework, and you can start using Flux immediately without a lot of new code.

---
1. Flux eschews MVC in favor of a unidirectional data flow.
2. The view propagates an action through a central dispatcher
3. Various stores that hold the application's data and business logic
4. Which updates all of the views that are affected

---

![inline fill](http://i942.photobucket.com/albums/ad261/szaranger/flux-simple-f8-diagram-explained-1300w.png)

---
# Enter Redux - Dan Abramov
![inline fill](https://d2eip9sf3oo6c2.cloudfront.net/instructors/avatars/000/000/032/bio/9VsY9i09.jpeg?1444932586)![inline fill](https://i.ytimg.com/vi/QvbsR77-VJw/maxresdefault.jpg)
![inline fill](http://az616578.vo.msecnd.net/files/2017/05/18/636307243128298924170874095_dumble2.jpg)![inline fill](https://i.ytimg.com/vi/n77lPqAe0rM/maxresdefault.jpg)

---
# Three Principles
![inline fill](https://media.giphy.com/media/3oD3YQjT2cSZTsy6Va/giphy.gif)

---
# 1. Single source of truth

```javascript
console.log(store.getState())

/* Prints
{
  visibilityFilter: 'SHOW_ALL',
  todos: [
    {
      text: 'Consider using Redux',
      completed: true,
    },
    {
      text: 'Keep all state in a single tree',
      completed: false
    }
  ]
}
*/
```

---
# 2. State is read-only
* The only way to change the state is to emit an action, an object describing what happened.

* Actions are just plain objects, they can be logged, serialized, stored, and later replayed for debugging or testing purposes.

```javascript
store.dispatch({
  type: 'COMPLETE_TODO',
  index: 1
})

store.dispatch({
  type: 'SET_VISIBILITY_FILTER',
  filter: 'SHOW_COMPLETED'
})
```

---
# 3. Changes are made with pure functions
* To specify how the state tree is transformed by actions, you write pure reducers.
* You can start with a single reducer, and as your app grows, split it off into smaller reducers that manage specific parts of the state tree.

---

```javascript
function visibilityFilter(state = 'SHOW_ALL', action) {
  switch (action.type) {
    case 'SET_VISIBILITY_FILTER':
      return action.filter
    default:
      return state
  }
}

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [
        ...state,
        {
          text: action.text,
          completed: false
        }
      ]
    case 'COMPLETE_TODO':
      return state.map((todo, index) => {
        if (index === action.index) {
          return Object.assign({}, todo, {
            completed: true
          })
        }
        return todo
      })
    default:
      return state
  }
}

import { combineReducers, createStore } from 'redux'
const reducer = combineReducers({ visibilityFilter, todos })
const store = createStore(reducer)
```

