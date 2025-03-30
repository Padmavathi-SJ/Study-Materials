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

### ice cream production company
```
let stocks = {
  Fruits : ["strawberry", "grapes", "banana", "apple"],
  liquids : ["water", "ice"],
  holder: ["cone", "cup", "stick"],
  toppings: ["chocolate", "peanuts"]
};

let is_shop_open = true;

function time(ms){
    return new Promise((resolve, reject) => {
        if(is_shop_open){
            setTimeout(resolve,ms)
        }
        else{
            reject(console.log("shop is closed!"));
        }
    })
}

async function kitchen(){
    try{
        await time(2000)
        console.log(`${stocks.Fruits[2]} was selected`)
        
        await time(0000)
        console.log("start the production");
        
        await time(2000)
        console.log("cut the fruit");
        
        await time(1000)
        console.log(`${stocks.liquids[0]} and ${stocks.liquids[1]} was added`)
        
        await time(1000)
        console.log("start the machine");
        
        await time(2000)
        console.log(`ice cream placed on ${stocks.holder[2]}`)
        
        await time(3000)
        console.log(`${stocks.toppings[1]} was added`)
        
        await time(2000)
        console.log("Ice cream is ready now!")
        
    }
    catch(error){
        console.log("customer left", error);
    }
    finally{
        console.log("day ended, shop is closed!");
    }
}

kitchen();

"""
banana was selected
start the production
cut the fruit
water and ice was added
start the machine
ice cream placed on stick
peanuts was added
Ice cream is ready now!
day ended, shop is closed!
"""
```
