# Passing Variables

One of the things I constantly struggle to remember and understand is the difference between passing variables by reference, by pointer, and by value. Today I tried to fix this by watching a [video](https://www.youtube.com/watch?v=KHZU1dnK4n0&t=1s) and an [articles](https://www.tutorialspoint.com/describe-pass-by-value-and-pass-by-reference-in-javascript) that helped me understand a lot more about the difference between the three. 

## Passing by value

A famous person once said its best to begin at the beginning. Now, jokes aside, passing by value is the simplest version of passing that exists. It requires an understanding of two things, memory and data. A value can be thought of as data and that data must be stored somewhere otherwise it is impossible to find! Everything on your computer is data and it all must be stored in memory. So, when we pass a variable by value what we are doing is giving each variable its own place in memory with that data. I will give you an example with some pseudo-code in c:

### Example
```c 
#include <stdio.h>

passbyvalue(int x) {

x = 1; // this x is one.

return x;
}

main(void){
int x = 5; // this x is 5
passbyvalue(x);
printf(x); //this x is 5! 

return 0;
}

```
### Explanation
Now you might wonder why I said this was the simplest to some of you this may not be intuitive at all. But remmeber when passing by value each declaration of a variable gets its own place in memory! No two are the same, so when we print these to the console, it will refer to the x in the same scope! Here is an image that dives a little deeper to help you understand this: 

### Image

![img](https://miro.medium.com/max/4028/1*AwvmeTkkHBptLwyq8BhP2Q.png)

## Reason for Studying this
 No you may be wondering about now why this is important to learn. It is because we need to understand whether a function will mutate the state of our code or not. If a function is given values passed by value then we that it will not mutate the global state. If the function is give values passed by reference then there is a chance that the function will mutate the global state. this means that our function may not be pure which can lead to some disadvantage or advantages depending on how you look at. But essentially the idea is that pure functions are easier to test and validate. you can think of a pure function like a look up table or a regular function in math. Theoretically all the results of the function could be put in a dictionary. However, if your function is not pure this cannot be the case.