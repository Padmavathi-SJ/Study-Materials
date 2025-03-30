## Async & Await

* Promise will work like -> resolve/reject -> inside if else
* for async function --> async(kyword) function(fn name) (){ try -> catch -> finally}

### example:
```
async function order() {
    try{
        await abc;
    }
    catch(error){
        console.log("abc function doesn't exist");
    }
    finally{
        console.log("runs code anyways");
    }
}
```

```
let stocks = {
  Fruits : ["strawberry", "grapes", "banana", "apple"],
  liquids : ["water", "ice"],
  holder: ["cone", "cup", "stick"],
  toppings: ["chocolate", "peanuts"]
};

let is_shop_open = true;

let toppings_choice = () => {
    return new Promise((resolve, reject)=>{
        setTimeout(() => {
            resolve(
            console.log("which topping would you love")
            );
        }, 3000);
    })
};

async function kitchen(){
    console.log(" A ");
    console.log(" B ");
    console.log(" C ");
    
    await toppings_choice()
    
    console.log(" D ");
    console.log(" E ");
}

kitchen()

console.log("doing the dishes");
console.log("cleaning the tables");
console.log("taking others orders");


"""
 A 
 B 
 C 
doing the dishes
cleaning the tables
taking others orders
which topping would you love
 D 
 E
"""
```
