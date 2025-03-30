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
