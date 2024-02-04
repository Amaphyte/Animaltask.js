// CREATION OF THE CLASS ANIMAL
class Animal {
    constructor(name, type, hasBackBone, isWarmBlooded) {
        this.name = name;
        this.type = type;
        this.hasBackBone = hasBackBone;
        this.isWarmBlooded = isWarmBlooded;
    }

    displayDetails() {
        return `I am a ${this.type} and my sound is ${this.name}`;
    }

    makeSound() {
        return "special generic sound";
    }
}

// THE APPLICATION OF INHERITANCE

// MAMMAL CLASS INHERITANCE
class Mammal extends Animal {
    constructor(name) {
        super(name, "Cat", true, true);
    }
}

// REPTILES CLASS INHERITANCE
class Reptile extends Animal {
    constructor(name) {
        super(name, "Tortoise", true, false);
    }
}

// AQUATIC CLASS INHERITANCE
class Aquatic extends Animal {
    constructor(name) {
        super(name, "Fish", false, true);
    }
}

// AVES CLASS INHERITANCE
class Aves extends Animal {
    constructor(name) {
        super(name, "Bird", true, true);
    }
}

// AMPHIBIANS CLASS INHERITANCE
class Amphibian extends Animal {
    constructor(name) {
        super(name, "Frog", true, true);
    }
}

// INSECTS CLASS INHERITANCE    
class Insect extends Animal {
    constructor(name) {
        super(name, "Butterfly", false, false);
    }
}

// INSTANTIATION OF VARIOUS SPECIES OF ANIMALS
const butterfly = new Insect("Flutters");
const frog = new Amphibian("Croak");
const bird = new Aves("Chirps");
const fish = new Aquatic("Drumming");
const tortoise = new Reptile("Hissing");
const cat = new Mammal("Meow");

// APPLICATION 
console.log(butterfly.displayDetails());
console.log(butterfly.makeSound());

console.log(frog.displayDetails());
console.log(frog.makeSound());

console.log(bird.displayDetails());
console.log(bird.makeSound());

console.log(fish.displayDetails());
console.log(fish.makeSound());

console.log(tortoise.displayDetails());
console.log(tortoise.makeSound());

console.log(cat.displayDetails());
console.log(cat.makeSound());
const readline = require('readline');

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

function interactWithUser() {
    rl.question("Enter the name of an animal (Butterfly, frog, bird, fish, tortise, cat): ", (userInput) => {
        switch (userInput.toLowerCase()) {
            case "flutters":
                displayAnimalDetails(butterfly);
                break;
            case "croak":
                displayAnimalDetails(frog);
                break;
            case "chirps":
                displayAnimalDetails(bird);
                break;
            case "drumming":
                displayAnimalDetails(fish);
                break;
            case "hissing":
                displayAnimalDetails(tortoise);
                break;
            case "meow":
                displayAnimalDetails(cat);
                break;
            default:
                console.log("Sorry, I don't recognize that animal name.");
        }
        rl.close();
    });
}

function displayAnimalDetails(animal) {
    console.log(animal.displayDetails());
    console.log(animal.makeSound());
}

// Call the interaction function
interactWithUser();
