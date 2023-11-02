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
    * Insert any variable or method by objectName.variable_or_mehod_name
    