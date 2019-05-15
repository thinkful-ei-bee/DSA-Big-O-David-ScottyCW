## What is the Big O for this?

### 1) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog, preferably of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You stand up and yell out, who here has a golden retriever and would like to be a playdate for my golden. Someone yells - "I do, be happy to bring him over"

O(1)

The big O is 1, because he yells, that's one action, with a response from anyone who has the right dog. 




### 2) Determine the Big O for the following algorithm: You are sitting in a room with 15 people. You want to find a playmate for your dog who is of the same breed. So you want to know if anyone out of the 15 people have the same breed as your dog. You start with the first person and ask him if he has a golden retriever. He says no, then you ask the next person, and the next, and the next until you find someone who has a golden or there is no one else to ask.

O(n)

the number of askings is in proportion to the number of people. it's a linear search. 


### 2. Even or odd

What is the Big O of the following algorithm? Explain your answer

```js
function isEven(value) {
    if (value % 2 == 0) {
        return true;
    }
    else
        return false;
    }
}
```

 O(1)

 Only it's either or, only one action. 


### 3. Are you here?

What is the Big O of the following algorithm? Explain your answer

```js
function areYouHere(arr1, arr2) {
    for (let i = 0; i < arr1.length; i++) {
        const el1 = arr1[i];
        for (let j = 0; j < arr2.length; j++) {
            const el2 = arr2[j];
            if (el1 === el2) return true;
        }
    }
    return false;
}
```
O(n^2)

It's nested loop, so it's n+n, each lop has n actions. so the big O is O(n^2)

### 4. Doubler 
What is the Big O of the following algorithm? Explain your answer

```js
function doubleArrayValues(array) {
    for (let i = 0; i < array.length; i++) {
        array[i] *= 2;
    }
    return array;
}

```
There is one loop, inside there are n actions to perform, 
so big O is O(n)

O(n)

### 5. Naive search
What is the Big O of the following algorithm? Explain your answer

```js
function naiveSearch(array, item) {
    for (let i = 0; i < array.length; i++) {
        if (array[i] === item) {
            return i;
        }
    }
}
```

Although it is likely the item needed to be found is at the beginning, but that is not always the case, the worst case would be when the item is at the end of the arry, then it will have to run n search. So, the big O is O(n)


### 6. Creating pairs:
What is the Big O of the following algorithm? Explain your answer

function createPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for(let j = i + 1; j < arr.length; j++) {
            console.log(arr[i] + ", " +  arr[j] );
        }
    }
}

It's a nested loop so the big O is O(n^2)


### 7. Compute the sequence
What does the following algorithm do? What is its runtime complexity? Explain your answer

```js
function compute(num) {
    let result = [];
    for (let i = 1; i <= num; i++) {

        if (i === 1) {
            result.push(0);
        }
        else if (i == 2) {
            result.push(1);
        }
        else {
            result.push(result[i - 2] + result[i - 3]);
        }
    }
    return result;
}
```
Although there are 3 conditionals inside this for loop, only one of them is triggered during each loop run, so the big O is 
O(n)

### 8. An efficient search
In this example, we return to the problem of searching using a more sophisticated approach than in naive search, above. Assume that the input array is always sorted. What is the Big O of the following algorithm? Explain your answer

```js
function efficientSearch(array, item) {
    let minIndex = 0;
    let maxIndex = array.length - 1;
    let currentIndex;
    let currentElement;

    while (minIndex <= maxIndex) {
        currentIndex = Math.floor((minIndex + maxIndex) / 2);
        currentElement = array[currentIndex];

        if (currentElement < item) {
            minIndex = currentIndex + 1;
        }
        else if (currentElement > item) {
            maxIndex = currentIndex - 1;
        }
        else {
            return currentIndex;
        }
    }
    return -1;
}
```


Because this is a binary search algo, no matter how big the array is, the out put of the big O has very insignificant difference. 

O(log(n))


9. Random element
What is the Big O of the following algorithm? Explain your answer

```js
function findRandomElement(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
}
```
because when this function is called, it only performs on computational action. So the big O is O(1)



### 10. What Am I?
What does the following algorithm do? What is the Big O of the following algorithm? Explain your answer

```js
function isWhat(n) {
    if (n < 2 || n % 1 != 0) {
        return false;
    }
    for (let i = 2; i < n; ++i) {
        if (n % i == 0) return false;
    }
    return true;
}
```

