# Code

Ylem is a no-code solution but as with every modern no-code solution, you still can write code if you want to:-)

From time to time you need to resort to complex data transformations. Say a single filter is not enough, so you can write custom Python 3.9 code with a full range of features over your data work.

This is what a "**Code**" task is for. It has an input as JSON, with which you can do whatever you want.

Let's say that we have the following dataset and see what we do with it.

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-26 at 18.01.11.png" alt=""><figcaption></figcaption></figure>

### Filtering

The simplest example can be achieved by using the "[Filter](filter.md)" block. But what if we need more complex filtering?&#x20;

Let's filter out rows of a type "invoice" that have an "amount" less than 2000:

```python
result = []

for i in input:
  if i["amount"] is not None and i["amount"] < 2000 and i["type"] == "invoice":
    result.append(i)

input = result
```

The result of the workflow above

<figure><img src="../../.gitbook/assets/python/Screenshot 2023-02-28 at 13.07.18.png" alt=""><figcaption></figcaption></figure>

### Aggregation

Let's calculate the total amount:

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

### Transformation

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

### Use Pandas

Yes, the "Code" supports [Pandas](https://pandas.pydata.org/) framework. This is how you can work with it and the input dataset:

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-29 at 20.43.59.png" alt=""><figcaption></figcaption></figure>

### Limitations

Our Python processor is based on [RestrictedPython](https://pypi.org/project/RestrictedPython/), therefore the "**Code**" task supports many standard Python libraries but not all of them. Let us know if you want to use something that is missing and we'll be happy to add it.

### Currently supported Python-modules

* json
* re
* time
* datetime
* pandas
