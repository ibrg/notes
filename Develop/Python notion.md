# Best practices
## Рекурсия
```
def length(list):
    if not list:
        return 0
    _, *tail = list
    return 1 + length(tail)


def reverse_range(begin, end):
    if begin == end:
        return [begin]
    return [end] + reverse_range(begin, end - 1)


def filter_positive(list):
    if not list:
        return []
    head, *tail = list
    if head > 0:
        return [head] + filter_positive(tail)
    return filter_positive(tail)

```

## Генератор списков
```
# квадраты чисел
[x*x for x in [1, 2, 3]]
# [1, 4, 9]

# Коды прописных букв из заданной строки
[ord(c) for c in "Hello!!" if c.isalpha() and c.islower()]
# [101, 108, 108, 111]

# Индексы пар, элементы которых равны друг другу
[i for i, (x, y) in enumerate([(1, 2), (4, 4), (5, 7), (0, 0)]) if x == y]
# [1, 3]
```
## Функции генераторы
```
# BEGIN
def my_map(function, source):
    for arg in source:
        yield function(arg)


def my_filter(condition, source):
    for arg in source:
        if condition(arg):
            yield arg


def replicate_each(number, source):
    for value in source:
        yield from (value for _ in range(number))
        # "yield from i", это сокращенная форма для
        #
        # for x in i:
        #     yield
```