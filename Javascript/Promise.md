### understand the steps

* Pending --> resolve/reject --> if resolve--> .then(), .then() till process completes, if reject--> catch(to handle errors) --> finally(either resolve or reject)
  
* Relationship between time and work (resolved)
* Promise chaining (.then --> .then--> .then etc)
* Error handling (if reject --> catch (to handle errors))
* finally handlerr (either get resolved or rejected)
  
```
let stocks = {
  Fruits : ["strawberry", "grapes", "banana", "apple"],
  liquids : ["water", "ice"],
  holder: ["cone", "cup", "stick"],
  toppings: ["chocolate", "peanuts"]
};

let is_shop_open = true;

let order = (time, work) => {
    return new Promise( (resolve, reject) => {
        if(is_shop_open){
            setTimeout(() => {
                 resolve(work());
            }, time);
        }
        else{
            reject(console.log("our shop is closed"))
        }
    })
};

order(2000, ()=>console.log(`${stocks.Fruits[0]} was selected`))

.then(() => {
    return order(0000, ()=>console.log("production has started"))
})

.then(() => {
    return order(2000, ()=>console.log("the fruit was choped"))
})

.then(()=>{
    return order(1000, ()=>console.log(`${stocks.liquids[0]} and ${stocks.liquids[1]} was selected`))
})

.then(() => {
    return order(1000, ()=>console.log("start the machine"))
})

.then(() => {
    return order(2000, ()=>console.log(`ice cream placed on ${stocks.holder[1]} `))
})

.then(() => {
    return order(3000, ()=>console.log(`${stocks.toppings[0]} added`))
})

.then(() => {
    return order(2000, ()=>console.log("Ice cream iwas served"))
})

.catch(() => {
    console.log("cosutomer left");
})

.finally(() => {
    console.log("Day ended, shop is closed!");
})

"""
strawberry was selected
production has started
the fruit was choped
water and ice was selected
start the machine
ice cream placed on cup 
chocolate added
Ice cream iwas served
Day ended, shop is closed!
"""
```
