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
