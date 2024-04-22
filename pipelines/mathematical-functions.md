# Mathematical functions

Several tasks such as **Aggregator**, **Condition,** and **Notification** support a powerful set of mathematical functions:

<figure><img src="../../.gitbook/assets/Screenshot 2022-10-01 at 18.35.09.png" alt=""><figcaption></figcaption></figure>

Most probably you are already familiar with them and used these ones in **SQL databases**, **Microsoft Excel**, or **Google Spreadsheets**.&#x20;

| Formula                                          | Meaning                                            | Example                |
| ------------------------------------------------ | -------------------------------------------------- | ---------------------- |
| **AVG(field\_name)**                             | Average value in the input data set                | AVG(amount)            |
| **SUM(field\_name)**                             | A sum of values in the input data set              | SUM(amount)            |
| **COUNT()**                                      | Number of rows in the input data set               |                        |
| **FIRST(field\_name)**                           | First value in the input data set                  |                        |
| **LAST(field\_name)**                            | Last value in the input data set                   |                        |
| **MAX(field\_name)**                             | Max value in the input data set                    | MAX(amount)            |
| **MIN(field\_name)**                             | Min value in the input data set                    | MIN(amount)            |
| **ROUND(field\_name, precision, "floor\|ceil")** | Round a number up or down with a certain precision | ROUND(tax, 2, "floor") |
| **NOW()**                                        | Current timestamp                                  |                        |

Also, there's an additional set of functions available for [Metrics](broken-reference) only:

<figure><img src="../../.gitbook/assets/Screenshot 2023-03-17 at 19.48.49.png" alt=""><figcaption></figcaption></figure>

| Formula                                         | Meaning                                                                                                                                              | Example                                                                    |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **METRIC\_AVG("period", duration)**             | This function returns an average value of this metric within a selected period of time                                                               | <p>METRIC_AVG("day", 5)<br>or <br>METRIC_AVG("month", 3)<br>etc.</p>       |
| **METRIC\_QUANTILE(level, "period", duration)** | This function returns a metric quantile within a selected period of time                                                                             | METRIC\_QUANTILE(0.25, "day", 7)                                           |
| **METRIC\_MEDIAN("period", duration)**          | <p>This function returns a median metric value within a selected period of time.</p><p></p><p>Alias for METRIC_QUANTILE(0.5, "period", duration)</p> | <p>METRIC_MEDIAN("day", 5)<br>or <br>METRIC_MEDIAN("month", 3)<br>etc.</p> |

