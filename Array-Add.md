# Push workaround for Liquid arrays

There is no 'add' filter, to add new items to your array.

But there is a concat filter, which concatenats two arrays.

With the 'split' filter, you can change every string into an array.

```
{% assign fruits = "apple" | split: ','%} <!-- only with the split, liquid sees this as an array -->
{% assign newfruit = "orange" | split: ',' %}

{% assign fruits = fruits | concat: newfruit %}
```

If you want to store more strings in fruits, just override `newfruit` and concat again.

This works also with `fruits = ""`.
