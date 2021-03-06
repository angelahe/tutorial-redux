# README notes
https://www.valentinog.com/blog/redux/
```
npx create-react-app react-redux
```

```
cd react-redux
npm i redux --save-dev
mkdir -p src/js/store
mkdir -p src/js/reducers
mkdir -p src/js/actions
mkdir -p src/js/constants
npm i react-redux --save-dev
mkdir -p src/js/components
npm i redux-thunk --save-dev
npm i redux-saga --save-dev
```

##Redux principles
2 - the only way to change the state is by sending a signal to the store (an action) - ie dispatching an action = sending a signal to the store
3 - the state is immutable and cannot change in place.

best practices:
- wrap every action within a function and takes name of action creator
- use concat, slice, spread operator for arrays
- use Object.assign or object spread of objects

key methods in Redux:
- getState - reading the current state of the application
- dispatch - for dispatching an action
- subscribe - for listening to state changes

from console:
store.getState();
store.subscribe(() => console.log('Look ma, Redux!!'));
store.dispatch( addArticle({ title: 'React Redux Tutorial for Beginners', id: 1 }) );
store.getState();

connect:
mapStateToProps - 
mapDispatchToProps - 

handleSubmit in Form.js

## middleware
used redux middleware to check the action payload before the action goes to the reducer

## asynchronous actions in redux with redux-thunk
return functions from action creators, and inside the function call APIs, delay the dispatch of an action etc.
can put API call directly inside an action creator

## using redux-saga middleware for managing side effects
used to deal with API calls, storage access
has clear separation between sychronous and asynchronous logic
uses generator functions - functions that can be paused and resumed on demand
replaces thunk implementation
implements worker function and watcher function
worker = call from redux-saga/effects
    when the data is loaded we can dispatch another action from our saga with put 
    worker sagas take the action as a parameter