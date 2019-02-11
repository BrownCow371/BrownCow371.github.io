---
layout: post
title:      "A deeper understanding of Thunk"
date:       2019-02-11 17:36:49 +0000
permalink:  a_deeper_understanding_of_thunk
---


> Redux Thunk middleware allows you to write action creators that return a function instead of an action. The thunk can be used to delay the dispatch of an action, or to dispatch only if a certain condition is met. The inner function receives the store methods dispatch and getState as parameters. - NPM

Thunk is a generic term  - it is a function that wraps an expression to delay its evaluation. 

**Example:**
```
// So instead of writing this:
let y = 5 * 6

//You’d write this:
let bar = () => 5 * 6;
```

In Redux, actions are just objects that include a “type” key and whatever else you need to include. Action creators are functions that return action objects (adds a layer of abstraction and makes actions less error prone). So instead of writing an action, you call a function that returns the action object for you.  

```
function actionCreator(){
     return {
          type: ‘MY_ACTION’,
          payload: ‘action info’
    }
}
```


> The synchronous and pure flow of data through Redux’s components is well-defined with distinct, simple roles. Action creators create objects → objects are dispatched to the store → the store invokes reducers → reducers generate new state → listeners are notified of state updates. - Gabriel Lebec

We use Thunk inside action creators so that our reducers remain pure functions even when the action creator is asynchronous (ie anything impure will be wrapped in thunk). Thunk looks at every action and if it is a function, it calls that function. 

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


You need to apply Thunk to your reducer using applyMiddleware. This ensures that whenever a value gets dispatched to the redux Store, it first passes through the provided middleware (in this case, Thunk):

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



