## Factory

The Factory method pattern provides an interface for creating objects that can be modified after creation. The cool thing about this is that the logic for creating our objects is centralized in a single place, simplifying and better organizing our code.

This pattern is used a lot and can also be implemented in two different ways, via classes or factory functions (functions that return an object).

```js

// Using classes

class Alien {
    constructor (name, phrase) {
        this.name = name
        this.phrase = phrase
        this.species = "alien"
    }
    fly = () => console.log("Zzzzzziiiiiinnnnnggggg!!")
    sayPhrase = () => console.log(this.phrase)
}

const alien1 = new Alien("Sandip", "I'm Sandip the alien!")
console.log(alien1.name) // output: "Sandip"

// Using factory function

function Alien(name, phrase) {
    this.name = name
    this.phrase = phrase
    this.species = "alien"
}

Alien.prototype.fly = () => console.log("Zzzzzziiiiiinnnnnggggg!!")
Alien.prototype.sayPhrase = () => console.log(this.phrase)

const alien1 = new Alien("Sandip", "I'm Sandip the alien!")

console.log(alien1.name) // output "Sandip"
console.log(alien1.phrase) // output "I'm Sandip the alien!"
alien1.fly() // output "Zzzzzziiiiiinnnnnggggg"

```
