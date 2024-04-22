# Transformer

**Transformer** is a powerful task that provides a set of conversion and transformation functionalities.

## Encoding to XML or CSV

Data is being sent between tasks in JSON format, but it is a very common use case to convert them to CSV or XML, for example, before sending them to someone as a report via Email or using them as an input for API endpoints.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.52.22.png" alt=""><figcaption></figcaption></figure>

## Casting to integer or string

Sometimes, when you aggregate some data it returns the result in a certain data format, but before sending it somewhere else, it is often necessary to convert it either to a string or to an integer.

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.55.12.png" alt=""><figcaption></figcaption></figure>

## Splitting a string into an array

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.58.01.png" alt=""><figcaption></figcaption></figure>

## Extracting and filtering data with GJSON

The secret sauce of our transformers is the integration with **GJSON** library that allows you to extract and filter any data from your dataset. More information about its syntax can be found in [their documentation](https://github.com/tidwall/gjson).

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 19.01.03.png" alt=""><figcaption></figcaption></figure>
