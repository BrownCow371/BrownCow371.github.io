---
layout: post
title:      "A deeper understanding of Thunk"
date:       2019-02-11 12:36:49 -0500
permalink:  a_deeper_understanding_of_thunk
---


> Redux Thunk middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters. - NPM

The work thunk is a generic term used to describe a function that wraps an expression to delay its evaluation. 

**Example:**
```
let y = 5 * 6

//the above expression can be wrapped in a function to become a thunk:
let bar = () => 5 * 6;
```

In Redux, actions are just objects that include a “type” key and whatever other data you need for that action. Action creators are functions that return action objects. They add a layer of abstraction and makesactions less error prone by allowing you to use one action creator evertime you want a specific action. So instead of writing an action, you call a function that returns the action object for you.  

```
function actionCreator(){
     return {
          type: ‘MY_ACTION’,
          payload: ‘action info’
    }
}
```


> The synchronous and pure flow of data through Redux’s components is well-defined with distinct, simple roles. Action creators create objects → objects are dispatched to the store → the store invokes reducers → reducers generate new state → listeners are notified of state updates. - Gabriel Lebec

We use Thunk inside action creators so that our reducers remain pure functions even when the action creator is asynchronous (i.e. anything impure will be wrapped in a thunk). The action creator is returning a function (which is pure as a reutrn value). Note that the invocation of that function may not be pure (like in the case of an asynchronous call to an API), but the function itself as a return value is. In addition to making the return value of the action creator pure, Thunk looks at every action called and if it returns a function, it calls that function (so that it doesn't have to be invoked manually).  

**Example:**

```
export function fetchActivities() {
    return (dispatch) => {
       dispatch({type: 'LOADING_DATA'});
       return fetch('/api/activities', {
            headers:{
            'Content-Type': 'application/json',
            'Accept': 'application/json'
            }
        })
        .then(checkStatus)
        .then(activities => dispatch({type: 'FETCH_ACTIVITIES', payload: activities}))
        .catch(err => {err.json().then(message  => dispatch({type: 'ACTIVITY_ERROR', payload: message}))})
    }
}
```

To set up Thunk, you need to first install it:

`npm install --save redux-thunk`

Then you need to import it and apply it to your reducer using applyMiddleware (which also needs to be imported). This ensures that whenever a value gets dispatched to the redux Store, it first passes through the provided middleware (in this case, Thunk):

```
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers/index';
 
const store = createStore(
  rootReducer,
  applyMiddleware(thunk)
);
```

Note that if you need to add multiple middlewares (like thunk AND dev tools) to your store, you need to also use compose. 

```
import thunk from 'redux-thunk';
import {createStore, applyMiddleware, compose} from 'redux';
import appReducer from './reducers/appReducer.js';

const composeEnhancers = window.__REDUX_DEVTOOLS_EXTENSION_COMPOSE__ || compose;
// create store using appReducer and Thunk
const store = createStore(appReducer, composeEnhancers(applyMiddleware(thunk)));
```


Resources 

* [https://www.npmjs.com/package/redux-thunk](https://www.npmjs.com/package/redux-thunk)

* [https://daveceddia.com/what-is-a-thunk/](https://daveceddia.com/what-is-a-thunk/)

* [https://medium.com/fullstack-academy/thunks-in-redux-the-basics-85e538a3fe60](https://medium.com/fullstack-academy/thunks-in-redux-the-basics-85e538a3fe60)



