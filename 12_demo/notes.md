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
