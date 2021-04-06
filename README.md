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
