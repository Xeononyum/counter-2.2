# counter-2.2
spwn counter implementation with 2.2 triggers usage


# Example Usage
```spwn
new_counter = import "new_counter.spwn"

num1 = new_counter(777)
num2 = new_counter(333)
num3 = new_counter(3i)

num3 = (num2*3/num2)+num1*255
num3 /= 2
num3++
num4 = num3 * 2
num4.display(90, 90)

```


Actually only aviable operators are `++, --, +=, -=, *=, /=, +, -, /, *`, and also `.display()` function. Also u can't do operations on numbers like that `77 *  counter1`, only `counter1 * 77`
