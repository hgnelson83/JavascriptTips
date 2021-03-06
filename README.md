# Javascript Tips 
Javascript Useful Snippets

# Grab HTML checkbox State
`<input type="checkbox" id="featured" name="featured" value="1" checked>`
```
<script>
    let checkbox = document.querySelector("#featured");
    checkbox.addEventListener("change", function() {
        this.value = this.checked ? 1 : 0;
        if(!this.checked) {
            this.removeAttribute('checked');
        } else {
            this.setAttribute('checked', '');
        }

    });
</script>
```
As always check the official docs: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox

# Copy/Clone an object in JS
```
//The object
const foods = { pizza: '🍕', pineapple: '🍍', watermelon: '🍉', meat: '🍖'};

// By using the spread operator
const myNewObject = {...foods};

//By using the assign function
const myNewerObject = Object.assign({}, foods);

// By using JSON.
const myNewestObject = JSON.parse(JSON.stringify(foods));

// Using the lodash JS library, provides a more efficient way to deep clone. More on that on: https://lodash.com/docs/#cloneDeep and
// https://www.digitalocean.com/community/tutorials/js-deep-cloning-javascript-objects
```
# Capitalize the first letter of a sentence in Javascript (one line)
```
let capitalize = (sentence) => sentence.charAt(0).toUpperCase() + sentence.slice(1);

capitalize('what does the fox say?'); // should return 'What does the fox say?'

```
# Execute or load a function after the DOM has loaded
```
window.addEventListener('DOMContentLoaded', () => myFunction());
```

# Adding multiple event listeners to different form fields in Javascript
```
document.querySelectorAll('#address, #city, #state').forEach(item => {
  item.addEventListener("blur", function() {
    console.log(`${item.id}`)
  })
})
```
# Check if an array of objects exists
returns a list of ids if it does.
Useful when working with API rest, and the backend expects an array of ids or numbers.
```
if(myArray.some(item => item.name)) { // would return true if it exists
    myArray = myArray.map(item => item.id);
}
```
# Check if an array exists
```
const isEmpty = (arr) => !Array.isArray(arr) || arr.length === 0;
isEmpty([]); // true
isEmpty([1, 2, 3]); // false
```
# Check interception of two array values. Or check if two arrays contain the same value.
```
let carModelsA = ["BMW", "Audi", "Opel", "Volkswagen", "Citroen", "Peugeot"];
let carModelsB = ["Suzuki", "Dacia", "Renault", "Volkswagen", "Mercedes", "Ferrari"];
carModelsA.filter(model => carModelsB.includes(model)); // returns ["Volkswagen"]
```
# Create a Multiply function, without using the * operator
```
let multiply = (a, b) => {
    let total = 0;
    const isPositive = Math.abs(b) == b; // returns a boolean
    
    for(let i=0; i < Math.abs(b); i++) {
        total = isPositive ? total + a : total - a;
    }
    return total;
}

// test function
multiply(-5,-4);

```
## Javascript Dates
### Get Current Day of the Week
```
const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
const today = new Date().getDay();
console.log(days[today]);
```
### Get Month
```
// JS months is zero-based (starts an index of zero)
const month = new Date().getMonth() +1
console.log(month);
```
### Get Year
```
const year = new Date().getFullYear();
console.log(year);
```
### Get Full Date
```
new Date().toDateString();
```
## Truncate a decimal to the nearest integer
```
let myDecimal = 14.7045454545455;
myDecimal.toFixed()-0; // returns 15
```
## Insert Objects to a Form Data
```

````
