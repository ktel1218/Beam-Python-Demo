# Overloading operators in python
## Overloading
In Python, certain operators can do different things when used on different types,
which is why this works:

```python
1 + 2
```

... As well as this:

```python
"apple" + "pie"
```

## DIY
We can do it ourselves. Lets make a node for a graph that can easily combine with another node, producing a third node that contains a combination of the first two nodes' children.

When we overload, we'll overload the magic method associated with that operator. For the plus operator, we override the magic method `__add__` on our class.

## Example

```python
class Node(object):

    def __init__(self, value, children=None):
        self.value = value
        if children is None:
            self.children = []
        else:
            self.children = children

    def __add__(self, other):
        return Node(self.children + other.children)
```

## Result
Now we can do this:

```python
node_a = Node(value="a", children=[Node(1),
                                   Node(2)])
node_b = Node(value="b", children=[Node(3),
                                   Node(4)])
new_node.children == [Node(1), Node(2),
                      Node(3), Node(4)]
```

## Real World Example
We could overload different operators. For example, the Beam SDK overloads bitwise operators. The following is a wordcount pipeline overloading the bitwise OR (`|`) and the bitwise RIGHT SHIFT (`>>`):

## In the Beam SDK

```python
p = beam.Pipeline(options=pipeline_options)

counts = (p | 'read' >> ReadFromText(file)
          | 'split' >> (beam.ParDo(WordExtractingDoFn()))
          | 'pair_with_one' >> beam.Map(lambda x: (x, 1))
          | 'group' >> beam.GroupByKey()
          | 'count' >> beam.Map(count_ones))
```
This code is using operator overloading to label each transform and then attach them to the pipeline in a streamlined, domain-specific way. Keep in mind this kind of "syntactic sugar" can be offputting to new developers looking for familiar Python.

## Source Code

Here's a link to the apache beam [github](https://github.com/apache/beam/blob/09fe4985f3698d6d1cb2722f2c010ba63d97d471/sdks/python/apache_beam/transforms/ptransform.py#L471) where they overload `__or__` and `__rrshift__` on the PTransform class.

