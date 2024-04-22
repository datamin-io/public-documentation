# Python

From time to time you need to resort to complex data transformations. Say a single filter is not enough, so you can write custom Python 3.9 code with a full range of features over your data work.

This is what a "Python" task is for. It has an input as JSON, with which you can do whatever you want. 

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-26 at 17.52.15.png" alt=""><figcaption></figcaption></figure>

To modify data, add a Python task onto the canvas, connect its input say to a Query task, and write your Python code in edit mode. You have complete (almost) freedom of action. You can, for example, filter the data. You can put a function on some keys. But let's go step by step. Let's say that we have this data set. What can we do with it?

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-26 at 18.01.11.png" alt=""><figcaption></figcaption></figure>

### Data filtration

The simplest example, which can be achieved by using the already existing Filter block. But let's do the same thing in Python. Let's filter out rows that have a value less than 2000. An example would be this code: 

```python
result = []

for i in input:
  if i["amount"] is not None and i["amount"] < 2000:
    result.append(i)

input = result
```

The result of the workflow above

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-28 at 13.07.18.png" alt=""><figcaption></figcaption></figure>

### Data aggregation

```python
total = 0

for i in input:
  if i["amount"] is not None:
    total += i["amount"]

input = {
  "total": total
}
```

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-28 at 13.11.08.png" alt=""><figcaption></figcaption></figure>

### Data transformation

```python
total = 0

for i in input:
  if i["amount"] is not None:
    total += i["amount"]

input = {
  "items": input,
  "total": total
}
```

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-28 at 13.13.13.png" alt=""><figcaption></figcaption></figure>

### Limitations

You can import standard Python modules, but not the `socket`.
