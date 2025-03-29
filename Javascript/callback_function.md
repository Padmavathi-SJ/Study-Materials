## callback relation with multiple function

### ice crream production
```
let stocks = {
  Fruits : ["strawberry", "grapes", "banana", "apple"],
  liquids : ["water", "ice"],
  holder: ["cone", "cup", "stick"],
  toppings: ["chocolate", "peanuts"]
};

let order = (Fruit_name, call_production) => {

  setTimeout(() => {
    console.log(`${stocks.Fruits[Fruit_name]} was selected`);

    call_production();

  }, 2000)

}

let production = () => {
  setTimeout(() =>{
    console.log("production has started");

  setTimeout(() => {
    console.log("fruit has been choped");

    setTimeout(() => {
      console.log(`${stocks.liquids[0]} and ${stocks.liquids[1]} was added`)

    setTimeout(() =>{
      console.log("The machine was started");
      
    setTimeout(() => {
        console.log(`icecream was placed on ${stocks.holder[0]} `);
    }, 2000)
    
    setTimeout(() => {
        console.log(`${stocks.toppings[0]} was added as toppings`);
    
    setTimeout(() => {
        console.log("server icecream");
    }, 2000)    


    }, 3000)
    }, 1000)
    }, 1000)
  }, 2000)
  }, 0000)

}

order(3, production);

"""
apple was selected
production has started
fruit has been choped
water and ice was added
The machine was started
icecream was placed on cone 
chocolate was added as toppings
server icecream
"""
```
