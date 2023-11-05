<img src="https://github.com/islamovsabit/oline-market-code/assets/147802380/ae336911-4632-4079-a947-35b05977ab67" />

### Medhot 1
##### ADD BASKET
- for version
```js
const cartButtons = document.querySelectorAll("[data-cart]");
const cartItems = document.querySelectorAll("[data-id]");
let resultBlock = document.querySelector(".classss");


for (let i = 0; i < cartButtons.length; i++) {
    const element = cartButtons[i];
    let ids = [];

    element.addEventListener("click", () => {
        const elementParent = element.parentElement;
        const proInfo = {
            id: elementParent.dataset.id,
            name: elementParent.querySelector('.name').innerText,
            surname: elementParent.querySelector('.surname').innerText,
            age: elementParent.querySelector('.age').innerText
        }
        const createdd = document.createElement('div')
        createdd.className = "created";
        resultBlock.appendChild(createdd)

        if (!ids.includes(proInfo.id)) {
            ids.push(proInfo.id);
            createdd.innerHTML += `<div class="big_doo" id="return_usname">
                <div class="name_d">name:&nbsp;<span>${proInfo.name}</span></div>
                <div class="surname_d">surname:&nbsp;<span>${proInfo.surname}</span></div>
                <div class="age_d">age:&nbsp;<span>${proInfo.age}</span></div>
            </div>`
        }
    });
}
```

### Medhot 2
##### ADD BASKET
- function version

```js
function addToCart(element) {
    const elementParent = element.parentElement;
    const proInfo = {
        id: elementParent.dataset.id,
        name: elementParent.querySelector('.name').innerText,
        surname: elementParent.querySelector('.surname').innerText,
        age: elementParent.querySelector('.age').innerText
    }

    const createdd = document.createElement('div');
    createdd.className = "created";
    resultBlock.appendChild(createdd);

    if (!ids.includes(proInfo.id)) {
        ids.push(proInfo.id);
        createdd.innerHTML += `<div class="big_doo" id="return_usname">
            <div class="name_d">name:&nbsp;<span>${proInfo.name}</span></div>
            <div class="surname_d">surname:&nbsp;<span>${proInfo.surname}</span></div>
            <div class="age_d">age:&nbsp;<span>${proInfo.age}</span></div>
        </div>`;
    }
}

const cartButtons = document.querySelectorAll("[data-cart]");
const cartItems = document.querySelectorAll("[data-id]");
let resultBlock = document.querySelector(".classss");
let ids = [];

for (let i = 0; i < cartButtons.length; i++) {
    const element = cartButtons[i];

    element.addEventListener("click", () => {
        addToCart(element);
    });
}
```

### Medhot 3
##### ADD BASKET
- class version
```js
class CartManager {
    constructor() {
        this.cartButtons = document.querySelectorAll("[data-cart]");
        this.cartItems = document.querySelectorAll("[data-id]");
        this.resultBlock = document.querySelector(".classss");
        this.ids = [];
        
        this.initializeEventListeners();
    }

    addToCart(element) {
        const elementParent = element.parentElement;
        const proInfo = {
            id: elementParent.dataset.id,
            name: elementParent.querySelector('.name').innerText,
            surname: elementParent.querySelector('.surname').innerText,
            age: elementParent.querySelector('.age').innerText
        }

        const createdd = document.createElement('div');
        createdd.className = "created";
        this.resultBlock.appendChild(createdd);

        if (!this.ids.includes(proInfo.id)) {
            this.ids.push(proInfo.id);
            createdd.innerHTML += `<div class="big_doo" id="return_usname">
                <div class="name_d">name:&nbsp;<span>${proInfo.name}</span></div>
                <div class="surname_d">surname:&nbsp;<span>${proInfo.surname}</span></div>
                <div class="age_d">age:&nbsp;<span>${proInfo.age}</span></div>
            </div>`;
        }
    }

    initializeEventListeners() {
        for (let i = 0; i < this.cartButtons.length; i++) {
            const element = this.cartButtons[i];

            element.addEventListener("click", () => {
                this.addToCart(element);
            });
        }
    }
}

// Usage:
const cartManager = new CartManager();
```




























