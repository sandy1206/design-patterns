## Singleton Pattern

this design pattern ensures there is only one single source of truth.
so class will have only on immutable instance which cant be copied or modified.

#### Implementation

In javascript we can use **Object.freeze()** to make instance immutable which we can not change later

```js
const Config = {
  start: () => console.log("App has started !!!!"),
  stop: () => console.log("App has stopped"),
};

// we freeze the object so to prevent the new properties to be added and copied

Config.freeze();

Config.start() // "App has started"
Config.update() // "App has updated"

Config.name = "Robert" // We try to add a new key
console.log(Config) // And verify it doesn't work: { start: [Function: start], update: [Function: update] }

```

```js

// there is an alternative way to implement singleton

let instance=null;

class Singleton{
	constructor(){
		if(!instance){
			instance= this;
		}else{
			return instance
		}
	}
}

let singleToneA= new Singleton();
let singleToneB= new Singleton();

console.log(singleToneA === singleToneB) //true

```

#### Use Cases

- Managing configuration setting
- Logger and error handling
- Database connection
- Caching
