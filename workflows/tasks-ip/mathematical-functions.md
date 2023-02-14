# Mathematical functions

Several tasks such as **Aggregator**, **Condition,** and **Notification** support a powerful set of mathematical functions:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.35.09.png" alt=""><figcaption></figcaption></figure>

Most probably you are already familiar with them and used these ones in **SQL databases**, **Microsoft Excel**, or **Google Spreadsheets**.&#x20;

| Formula                                          | Meaning                                                                                                                                     | Example                                                              |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **AVG(field\_name)**                             | Average value in the input data set                                                                                                         | AVG(amount)                                                          |
| **SUM(field\_name)**                             | A sum of values in the input data set                                                                                                       | SUM(amount)                                                          |
| **COUNT()**                                      | Number of rows in the input data set                                                                                                        |                                                                      |
| **FIRST(field\_name)**                           | First value in the input data set                                                                                                           |                                                                      |
| **LAST(field\_name)**                            | Last value in the input data set                                                                                                            |                                                                      |
| **MAX(field\_name)**                             | Max value in the input data set                                                                                                             | MAX(amount)                                                          |
| **MIN(field\_name)**                             | Min value in the input data set                                                                                                             | MIN(amount)                                                          |
| **ROUND(field\_name, precision, "floor\|ceil")** | Round a number up or down with a certain precision                                                                                          | ROUND(tax, 2, "floor")                                               |
| **NOW()**                                        | Current timestamp                                                                                                                           |                                                                      |
| **METRIC\_AVG("period", duration)**              | This function is available in [metrics](broken-reference) only and returns an average value of this metric within a selected period of time | <p>METRIC_AVG("day", 5)<br>or <br>METRIC_AVG("month", 3)<br>etc.</p> |
|                                                  |                                                                                                                                             |                                                                      |

****

****

