Outer most loop to inner most loop is the order in which nested loops are processed in python.

```python
L = [i + j for i in range(2) for j in range(5)]
```

unrolled looks like this

```python
L = []  # Start with an empty list

for i in range(2):  # Outer loop
    for j in range(5):  # Inner loop
        L.append(i + j)  # Append the sum of i and j to the list
```

Structure for all list comprehension: [{expression} {iteration} {condition}]
{expression} can be anything that will return a single object
{iteration} is evaluated from outer most loop to the inner most loop
{condition} this is boolean filter that is applied to the variable after 'for'

LIST COMPREHENSION IS NOT RUN LEFT TO RIGHT. seems like it's more like {iteration} then {condition} then {expression}

```python
[word for word in words if len(word) <= 3]
```

So, unrolled, the above list comprehension would look like
```python
list = []
for w in words:
	if len(word) <= 3:
		list.append(word)
```