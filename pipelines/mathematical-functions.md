# Mathematical functions and operations

Several tasks such as **Aggregator**, **Condition,** and **Notification** are empowered by an extended mathematical editor that supports a powerful set of mathematical functions and operations.

## Mathematical functions

<figure><img src="../.gitbook/assets/Screenshot 2024-06-21 at 22.19.25.png" alt=""><figcaption></figcaption></figure>

Most probably you are already familiar with them and used these ones in **SQL databases**, **Microsoft Excel**, or **Google Spreadsheets**.&#x20;

### Array functions

| Formula                | Meaning                               | Example     |
| ---------------------- | ------------------------------------- | ----------- |
| **AVG(field\_name)**   | Average value in the input data set   | AVG(amount) |
| **SUM(field\_name)**   | A sum of values in the input data set | SUM(amount) |
| **COUNT()**            | Number of rows in the input data set  |             |
| **FIRST(field\_name)** | First value in the input data set     |             |
| **LAST(field\_name)**  | Last value in the input data set      |             |
| **MAX(field\_name)**   | Max value in the input data set       | MAX(amount) |
| **MIN(field\_name)**   | Min value in the input data set       | MIN(amount) |

### Single number functions

| Formula                                          | Meaning                                                                             | Example                |
| ------------------------------------------------ | ----------------------------------------------------------------------------------- | ---------------------- |
| **ROUND(field\_name, precision, "floor\|ceil")** | Round a number up or down with a certain precision                                  | ROUND(tax, 2, "floor") |
| **ABS(field\_name)**                             | The absolute value of a number                                                      |                        |
| **NEG(field\_name)**                             | Inverts the sign of a number. From "-" to "+" and other way around                  |                        |
| **SIGN(field\_name)**                            | <p>Returns:</p><pre><code>-1 if d &#x3C;  0
 0 if d == 0
+1 if d >  0
</code></pre> |                        |
| **STRING(field\_name)**                          | Converts number to string                                                           |                        |
| **INT(field\_name)**                             | Returns an integer part of a decimal number                                         |                        |

### Other functions

| Formula     | Meaning                                                     | Example                 |
| ----------- | ----------------------------------------------------------- | ----------------------- |
| **ENV()**   | Use environment variable in a format of ENV\_variable\_name | ENV\_REVENUE\_THRESHOLD |
| **NOW()**   | Current timestamp                                           |                         |
| **INPUT()** | The entire input data set as JSON                           |                         |

### Metric functions

Also, there's an additional set of functions available for [Metrics](broken-reference) only:

<figure><img src="../.gitbook/assets/Screenshot 2023-03-17 at 19.48.49.png" alt=""><figcaption></figcaption></figure>

| Formula                                         | Meaning                                                                                                                                              | Example                                                                    |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **METRIC\_AVG("period", duration)**             | This function returns an average value of this metric within a selected period of time                                                               | <p>METRIC_AVG("day", 5)<br>or <br>METRIC_AVG("month", 3)<br>etc.</p>       |
| **METRIC\_QUANTILE(level, "period", duration)** | This function returns a metric quantile within a selected period of time                                                                             | METRIC\_QUANTILE(0.25, "day", 7)                                           |
| **METRIC\_MEDIAN("period", duration)**          | <p>This function returns a median metric value within a selected period of time.</p><p></p><p>Alias for METRIC_QUANTILE(0.5, "period", duration)</p> | <p>METRIC_MEDIAN("day", 5)<br>or <br>METRIC_MEDIAN("month", 3)<br>etc.</p> |

## Arithmetical and logical operations

The following list is supported:

### Arithmetic

\+\
\-\
/\
\*\
%\
\*\*

### Comparison

\==\
\===\
!=\
!==\
\>\
<\
\>=\
<=\
\>==\
<==

### Boolean operators

||\
&&\
!

### Bitmasking

|\
&\
^\
<<\
\>>

## Regular expression comparison

The following two operations are supported for searching in strings with regular expressions

\=\~     // means a regular expression match is found\
!\~      // means a regular expression match is not found

For example, the following string placed in the Condition or Aggregator will return `true`

```regex
"Mountaineering is the best sport in the world. Or engineering?" =~ "[(Engin|Mountain)]eering\\s"
```

Supported syntax for regular expressions: [https://pkg.go.dev/regexp/syntax](https://pkg.go.dev/regexp/syntax).

## Formatting of dates

Comparison operations can also be used for comparing dates. The following formats are supported:

* time.UnixDate,&#x20;
* time.RubyDate,&#x20;
* time.Kitchen,&#x20;
* time.RFC3339,&#x20;
* time.RFC3339Nano,&#x20;
* "2006-01-02", // RFC 3339&#x20;
* "2006-01-02 15:04", // RFC 3339 with minutes&#x20;
* "2006-01-02 15:04:05", // RFC 3339 with seconds&#x20;
* "2006-01-02 15:04:05-07:00", // RFC 3339 with seconds and timezone&#x20;
* "2006-01-02T15Z", // ISO8601 with hour without UTC offset&#x20;
* "2006-01-02T15:04Z", // ISO8601 with minutes without UTC offset&#x20;
* "2006-01-02T15Z0700", // ISO8601 with hour&#x20;
* "2006-01-02T15:04:05Z", // ISO8601 with seconds without UTC offset&#x20;
* "2006-01-02T15:04Z0700", // ISO8601 with minutes&#x20;
* "2006-01-02T15:04:05Z0700", // ISO8601 with seconds&#x20;
* "2006-01-02T15:04:05.999999999Z", // ISO8601 with nanoseconds without UTC offset&#x20;
* "2006-01-02T15:04:05.999999999Z0700", // ISO8601 with nanoseconds
