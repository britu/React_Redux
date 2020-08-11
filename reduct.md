import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';
import {createStore} from 'redux'; 
// Step 1 :It will take reducer from store



//ACTION Increment : is a function that return object
const increment=() =>{
  return{
    type:'INCREMENT'
  }
}

const decrement = () =>{
  return{
    type: 'DECREMENT'
  }
}


//REDUCER how your action this action gonna be called 
// Reducer would check and modify it from store
//REDUCER
const counter = (state = 0, action)=>{
  switch(action.type){
    case 'INCREMENT':
      return state + 1;
    
    case 'DECREMENT':
      return state - 1;
  }
}

//STORE -> Globalized State : Now actually add it to the store so store let's
let store = createStore(counter);

//DISPLAY it in the consloe
store.subscribe(() => console.log(store.getState()));


//DISPATCH
store.dispatch(increment());
store.dispatch(decrement());
store.dispatch(decrement());

// DISPACH this action to reducer and store get updated

