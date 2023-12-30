# counter-2.2
spwn counter implementation with 2.2 triggers usage


# Example Usage
```spwn
new_counter = import "new_counter.spwn"

time = new_counter(30, true)
item = new_counter(20, false)

time2 = item + time
time3 = item + 1.2
not_time = item + 7
not_time2 = item / 2

time2.display(90,90)
time3.display(120,90)
not_time.display(150,90)
not_time2.display(180,90)
```


Actually only aviable operators are `++, --, +=, -=, *=, /=, +, -, /, *`, and also `.display()` function. Also u can't do operations on numbers like that `77 *  counter1`, only `counter1 * 77`

if second argument is true, it will use time counter instead of item

if one of operands in +, -, *, / operators is time counter or float number, result will be too time counter

time counter only means that it can contain float values and also separated from items
