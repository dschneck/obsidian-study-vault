What is a derivative - if you slightly bump up the input to a function, how much does the output change

magic methods - class methods in python that have special significance and can be overwritten. Common examples are `__str__` for printing out pretty strings and  `__add__` for operator overloading the `+` 

mangling mangling - a mechanism in python that prepends the class name to a class attribute that starts with `__`. For example:

`class MyClass:
    `def __init__(self):
        `self.__private = 42

    def get_private(self):
        return self.__private
`
Internally, the `__private` attribute is renamed to `_MyClass__private`. This means that it is not easily accessible from outside the class using its original name.

topological sort - of a [directed graph](https://en.wikipedia.org/wiki/Directed_graph "Directed graph") is a [linear ordering](https://en.wikipedia.org/wiki/Total_order "Total order") of its [vertices](https://en.wikipedia.org/wiki/Vertex_(graph_theory) "Vertex (graph theory)") such that for every directed edge _(u,v)_ from vertex _u_ to vertex _v_, _u_ comes before _v_ in the ordering

it's used to call the backward functions for each node starting from the end of the graph

