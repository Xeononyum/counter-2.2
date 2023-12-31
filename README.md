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

floored_time3 = time3.floor()
rounded_time3 = time3.round()
ceiled_time3 = time3.ceil()

positive_time3 = time3.abs()
negative_time3 = time3.neg()

time2.display(90,90)
time3.display(120,90)
floored_time3.display(150, 90)
not_time.display(180,90)
not_time2.display(210,90)
```


Actually only aviable operators are `++, --, +=, -=, *=, /=, +, -, /, *`, and also `.display(), .floor(), .round(), ceil(), .abs(), .neg()` macros. Also u can't do operations on numbers like that `77 *  counter1`, only `counter1 * 77`

`new_counter(1, false)` - integer number counter with value 1
`new_counter(1.5, true)` - float number counter with value 1.5

`new_counter(1i, false)` - integer number counter that uses item 1
`new_counter(1i, true)` - float number counter that uses time 1

Note: time and item not intersected, so if u have `new_counter(3i, false)` it wont be equal to `new_counter(3i, true)`

operators `+, -, *, /`` returns time counter if one of provided arguments are float number or time counter:
```spwn
 my_counter = new_counter(77, false) * 3.5
 my_counter.is_time // true
```

if `.floor, .ceil, .round, .abs, .neg` called on time counter, returned counter will also be time, otherwise - item

operators `+=, -=, *=, /=, ++, --` dont change counter type:
```spwn
 my_counter = new_counter(3, false)
 my_counter.is_time // false
 my_counter /= 1.7
 my_counter.is_time // false
```

Dont create time counters with more than 3 digits after decimal point, it resets after u save level in game, but while game running time counters is just float

`my_counter = new_counter(3.141592)` - bad
`my_counter = new_counter(3141592) / 1000000` - not so good, because big numbers can work unexpectedly 
`my_counter = new_counter(3141.592) / 1000` - best

Also number displays can't show more than 2 digits after decimal point, so if u need to check is value right, better multiply it by some number and then display it