### Notes
1. String -> 
    * ${} insert variable in String
    * charAt() -> pass index
    * indexOf() -> pass letter
    * substring(x, y) -> x=starting point y=endindex
    * slice(x, y) -> return a new arraay x=starting point from 0 y=endpoint without considering given point
    * splice(x,y) -> return a new arraay x=starting point from 0 y=endpoint with considering given point
    * trim() -> work like condense
    * replace(x,y) -> x=want to replace y=need this replacement
    * includes(x) -> x=check it exisi or not & return boolen value
    * split(x) -> x=separator & return splited value in array

2. Array -> 
    * push(x) -> insert x in array
    * pop() -> remove last value from array
    * unshift(x) -> insert x on start position
    * shift() -> remove first value
    * includes(x) -> check x is available or not in array
    * join() -> convert array into string
    * slice(x,y) -> x=start index y=end index RETURN NEW ARRAY
    * splice(x,y) -> x=start_index y=end_index CHANGES HAPPEN IN EXISTING ARRAY
    * spread operator -> is array [...myArray1, ...myArray2] combine two array in new array
    * flat(Infinity) -> destructuring nested array in new single array
    * isArray -> conditional check is it array
    * from(x) -> return an array from any object. x=string if object return an empty array 
    * Array.of(x, y, z) -> props are variable which is convert into an array 

3. Object ->
    * access object property by two .props_name & ["props_name"]
    * Object.freeze -> existing properties non-writable and non-configurable
    * insert any variable or method(call back function) by objectName.variable_or_method_name
    * you can access nested object value by simply objectName.variableName
    * combine multiple object by Object.assign({}, obj1, obj2, obj4) => Return a given (empty) object
    * spread is also useful in object as {...obj1, ...obj2} => store in new object and modify(insert or update) keyValue pair
    * Object.keys(objectName) => return all keys in array format
    * Object.values(objectName) => return all values in array format
    * Object.entries(objectName) => return key value pair of object in array format as [ [ 'id', '123abc' ], [ 'name', 'Sammy' ], [ 'isLoggedIn', false ] ]
    * Object.hasOwnProperty('x') => return boolean value if given x property exist in object
    * destructuring object is following way => const {courseInstructor: instructor, price: p} = objectName then simply access it by variable name => instructor

4. Function ->
    * nothing but block of code which take input as argument(variable, object, array) & output as return value
    * default value in argument as functionName(val=1, val2=2)
    * if you want multiple value as a input functionName(val1, val2, ...num1) => num1 hold a value as [x, y, z]

5. Scope ->
    * scope is define within if-else, function & loop(iteration) => outside variable within scope is accesible but revserse is not possible (variableName is not define error)
    *  function functionName(x) {return x} => function defination is write anywhere is possible in file -> not restrict to define 1st & then call functionName() || if you can store function in variable, that time defination is must before accessing variable as function. because during memory creation phase within execution context -> function as variable initialize as undefine but regular function treat as definaiton -> at time of execution of function(execution phase) create there own execution context. i.e  when initialize variable as a function during execution phase that time function execute in (new) execution context and set function return value in variable.  <--Interesting Section>

6. Arrow -> 
    * function within object has right's to access there parent variable with the help of this keyword = rexical scope. Within function this => return parent object with all variable & functions

            {
                username: 'sam',
                price: 999,
                welcomeMessage: [Function: welcomeMessage]
            }

    * this in gloabl file, return a empty {} object & within browser return window object
    * this within function return multiple values sunch as global[], fun-> clearInterval, clearTimeout, setInterval, setTimeout, clearImmediate, setImmediate & performance{}
    * arrow function also return this as empty {} object
    * if you can use {} in arrow function that case return keyword is must. but in single line with () and without () is possible.
7. Control flow ->
    * && || in if condition => if (userLoggedIn && debitCard || 2==3) 
    * switch case 
    * truthy values => "0", 'false', " ", [], {}, function(){}
    * falsy values => false, 0, -0, BigInt 0n, "", null, undefined, NaN
    * how to check empty object => 

        const emptyObj = {}

        if (Object.keys(emptyObj).length === 0) {
            console.log("Object is empty");
        }
    * terniary operator => condition ? true : false
8. Iteration ->
    * for loop => for (let index = 0; index < myArray.length; index++) {}
    * while => while (arr < myArray.length) {arr = arr + 1}
    * do while => do {score++} while (score <= 10);

    * for loop on array => const arr = [1, 2, 3, 4, 5]
        for (const num of arr) {console.log(num)}
    * for loop on string => const greetings = "Hello world!"
        for (const greet of greetings) {log(greet)}
    * for loop on map => const map = new Map()
        map.set('IN', "India") 
        for (const [key, value] of map) {log(key, value)}
    * for on object => <b> myObject is not iterable</b>
        <code>
        const myObject = {game1: 'NFS'    game2: 'Spiderman'}
        for (const [key, value] of myObject) {log(key, value)}</code>
    * if you want to iterate object => 
        <code>
        const myObject = {js: 'javascript',cpp: 'C++',rb: "ruby", swift: "swift by apple"}

        for (const key in myObject) {
            console.log(`${key} shortcut is for ${myObject[key]}`);
        }
        </code>
    * also useful for array =>
        <code>
            const programming = ["js", "rb", "py", "java", "cpp"] <br>
            for (const key in programming) {
                console.log(programming[key]);
            }
        </code>
    * <b>it is not possible with map</b> <code>for (const key in map) {}</code>
    * forEach on array => <code>[].forEach((value)=> log(value))</code>
    * how to pass function in forEach() => 
    <code>

        const coding = ["js", "ruby", "java", "python", "cpp"]
        function printMe(item){
        console.log(item)}
        coding.forEach(printMe) 
    </code>

    * in each interation get value, index, arr => 
    <code>

        coding.forEach( (item, index, arr)=> {
            console.log(item, index, arr);
        })
    </code>
    * iterate array of object => myCoding is array of object
    <code>

        myCoding.forEach( (item) => {
        console.log(item.<objectPropertyName>)})
    </code> 
    * forEach() is not useful for filtering data, it never store return data in new variable. If you want store iterable value in new array that time you can go through [].push(value) =>
    <code>
    
        const values = coding.forEach( (item) => console.log
        (item))
        => undefined
    </code>
    * filter data by filter() =>
    <code>

        const newNums = myNums.filter( (num) => {
            return num > 4} )
    </code>
    * [].map() use for perform action within map, you can also use multiple map on same array => 
    <code>

        const newNums = myNumers
        
                        .map((num) => num * 10 )
                        .map( (num) => num + 1)
                        .filter( (num) => num >= 40)
    </code>

    * reduce is use to calculate sum of all array value with the help of holding previous calculated value => 
    <code>

        const myTotal = myNums.reduce( (acc, curr) => acc+curr, 0)
    </code>

9. DOM ->
    
    * how to access html element wich is associated with className => 
    <code>
    
        *   const parent = document.querySelector('.parent') => retun complete element with child
    </code>
    <code>

        *   parent.children => return HTML collection
    </code>
        *   access one of child from parent element => parent.children[0].innerHTML (use loop to access all child)
        *   how to change style of parent => parent.children[1].style.color = "orange"
        *   first & last element of child (return HTML element) => parent.firstElementChild & parent.lastElementChild
        *   if one class used for multiple element
            *   const dayOne = document.querySelector('.day') => return first element
            *   dayOne.parentElement => return parent element
            *   dayOne.nextElementSibling => return 2nd element
            *   parent.childNodes => return children in the form of node list[]
        *   create element in script => document.createElement('div')
        *   add class,id & setAttribute +> div.className = 'main', div.id = Math.round(Math.random() * 10 + 1), div.setAttribute("title", generated title)
        *   add style => div.style.backgroundColor = "green", div.style.padding = "12px"
        *   create text node => const addText = documet.createTextNode("text")
        *   add text node in created element => div.appendChild(addText)
        *   append created element in body => document.body.appendChild(div)
        *   write a function which use to add element in html tag => 
    <code>

            function addLanguage(langName){
                const li = document.createElement('li');
                li.innerHTML = `${langName}`
                document.querySelector('.language').appendChild(li)
            }
            addLanguage("python")
            addLanguage("typescript")
    </code>
        *   updated version => create li element-> create text node as well as append in li-> access element by className at same time append li inside it.
    <code>

            function addOptiLanguage(langName){
                const li = document.createElement('li');
                li.appendChild(document.createTextNode(langName))
                document.querySelector('.language').appendChild(li)
            }
            addOptiLanguage('golang')
    </code>
        *   when you need to get 2nd child of li =>
        <code>
            const secondLang = document.querySelector("li:nth-child(2)")
        </code>
        *   edit 2nd-li(create element & replace it) => 
        <code>

            const newli = document.createElement('li')
            newli.textContent = "Mojo"
            secondLang.replaceWith(newli)
        </code>
        *   edit by outerHTML =>
        <code>

            const firstLang = document.querySelector("li:first-child")
            firstLang.outerHTML = `<li>TypeScript</li>`
        </code>
        *   remove element =>
        <code>

            const lastLang = document.querySelector('li:last-child')
            lastLang.remove()
        </code>

10. Project ->
    *   not added anything yet here.

11. Events ->
    *   onClick event => access element by getElementById('owl')
    <code>
            document.getElementById('owl').onclick = function(){alert("owl clicked")}
    </code>
    *   event propagation e.stopPropagation() => stop bubbling & e.preventDefault() => stop default behaviour
    <code>
        document.getElementById('images').addEventListener('click', function(e){
            console.log("clicked inside the ul");
        }, false)

        document.getElementById('owl').addEventListener('click', function(e){
            console.log("owl clicked");
            // e.stopPropagation()
        }, false)
        
        document.getElementById('google').addEventListener('click',function(e){
            e.preventDefault();
            e.stopPropagation()
            console.log("google clicked");
        }, false)
    </code>
    *   remove img element with li =>
    <code>
        document.querySelector('#images').addEventListener('click', function(e){
            console.log(e.target.tagName);
            
            if (e.target.tagName === 'IMG') {
                console.log(e.target.id);
                let removeIt = e.target.parentNode
                removeIt.remove()
            }
        })
    </code>
    *   How to write code in js_Script => create a fun which is store in one variable & call it by funName()
    *   how to change text based on time using setTimeout => 
    <code>

        const changeText = function(){
            document.querySelector('h1').innerHTML = "best JS series"
        }

        const changeMe = setTimeout(changeText, 2000)
    </code>
    *   stop execution based on time =>
    <code>
    
        document.querySelector('#stop').addEventListener('click', function(){
            clearTimeout(changeMe)
            console.log("STOPPED")
        })
    </code>
    </code>
    *   start & stop execution based on click(setInterval & clearInterval) => 
    <code>

        document.querySelector('#start').addEventListener('click', () => {
            console.log('start');
            const intervalId = setInterval(sayDate, 2000)

            document.querySelector('#stop').addEventListener('click', () => {
                console.log('Stopped');
                clearInterval(intervalId)
            })
        })
    </code>

12. Advance One ->
    *   promise -> manage situations where you must wait for the outcome of an operation.
    *   promise has one call back function, that function take two parameter resolve & reject.
    *   first execute promise, then .then() execute => 
    <code>

        const promiseOne = new Promise(function(resolve, reject){

            setTimeout(function(){
                console.log('Async task is compelete');
                resolve()
            }, 1000)})

        promiseOne.then(function(){
            console.log("Promise consumed");
        })
    </code>
    *   2nd way to write =>
    <code>

        new Promise(function(resolve, reject){
            setTimeout(function(){
                console.log("Async task 2");
                resolve()
            }, 1000)

        }).then(function(){
            console.log("Async 2 resolved");
        })
    </code>
    *   resolve return value =>
    <code>

        const promiseThree = new Promise(function(resolve, reject){
            setTimeout(function(){
                resolve({username: "Chai", email: "chai@example.com"})
            }, 1000)
        })

        promiseThree.then(function(user){
            console.log(user.username);
        })
    </code>
    *   multiple .then() use =>
    <code>
        const promiseFour = new Promise(function(resolve, reject){
            setTimeout(function(){
                let error = false
                if (!error) {
                    resolve({username: "hitesh", password: "123"})
                } else {
                    reject('ERROR: Something went wrong')
                }
            }, 1000)
        })

        promiseFour
        .then((user) => {
            console.log(user);
            return user.username
        }).then((username) => {
            console.log(username);
        }).catch(function(error){
            console.log(error);
        }).finally(() => console.log("The promise is either resolved or rejected"))
    </code>
    *   catch error is must, when you specify reject in promise defination =>
    <code>

        const promiseFive = new Promise(function(resolve, reject){
            setTimeout(function(){
                let error = false
                if (!error) {
                    resolve({username: "javascript", password: "123"})
                } else {
                    reject('ERROR: JS went wrong')
                }
            }, 1000)
        });
        promiseFive.then((value)=> console.log(value)).catch((err)=> console.log(err))
    </code>
    *   how to use async & await =>
    <code>
        async function consumePromiseFive(){
           
            try {
                const response = await promiseFive
                console.log(response);
            } catch (error) {
                console.log(error);
            }
        }

        consumePromiseFive()
    </code>
    *   2nd example => 
    <code>

        async function getAllUsers(){
            try {
                const response = await fetch('https://jsonplaceholder.typicode.com/users')

                const data = await response.json()
                console.log(data);
            } catch (error) {
                console.log("E: ", error);
            }
        }

        getAllUsers()
    </code>
    *   api request =>
    <code>

        const requestUrl = 'https://api.github.com/users/hiteshchoudhary'
        const xhr = new XMLHttpRequest();
        xhr.open('GET', requestUrl)
        xhr.onreadystatechange = function(){
            
            console.log(xhr.readyState);
            if (xhr.readyState === 4) {
                const data = JSON.parse(this.responseText)
                console.log(typeof data);
                console.log(data.followers);
            }
        }
        xhr.send();
    </code>

13. Class & OOPS ->
    *   constructor of class execute during when instance of class created
    <code>

        class User {
            constructor(username, email, password){
                this.username = username;
                this.email = email;
                this.password = password
            }

            encryptPassword(){
                return `${this.password}abc`
            }
            changeUsername(){
                return `${this.username.toUpperCase()}`
            }

        }

        const chai = new User("chai", "chai@gmail.com", "123")
    </code>
    *   access method of class by className.methodName =>log(chai.encryptPassword());
    *   behind the scene method which is written inside the class, that method act as a function such as className.prototype.funcName = function which return a value =>
    <code>

        User.prototype.encryptPassword = function(){
            return `${this.password}abc`
        }
    </code>
    *   create one object which use to access value of class =>
    <code>

        const tea = new User("tea", "tea@gmail.com", "123")
        console.log(tea.encryptPassword());
    </code>
    *   object with example =>
    <code>

        function createUser(username, score){
            this.username = username
            this.score = score
        }

        createUser.prototype.increment = function(){
            this.score++
        }
        createUser.prototype.printMe = function(){
            console.log(`price is ${this.score}`);
        }

        const chai = new createUser("chai", 25)
        const tea = createUser("tea", 250)

        chai.increment()
        chai.printMe()
    </code>
    *   when log(this) within function and that function located within object return scope of global class
    *   return a object =>
    <code>
        function User(username, loginCount, isLoggedIn){
            this.username = username;
            this.loginCount = loginCount;
            this.isLoggedIn = isLoggedIn

            this.greeting = function(){
                console.log(`Welcome ${this.username}`);

            }

            return this
        }

        const userOne = new User("hitesh", 12, true)
        const userTwo = new User("ChaiAurCode", 11, false)
        console.log(userOne);
        console.log(userTwo);
    </code>
        
        this return a object => 
        
        User {
            username: 'hitesh',
            loginCount: 12,
            isLoggedIn: true,
            greeting: [Function (anonymous)]
            }