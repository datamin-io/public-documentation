# Environment variables

Environment variables allow you to set variables in one place and reuse it in workflows and metrics as **ENV\_variable\_name**.

<figure><img src="../.gitbook/assets/Screenshot 2022-12-09 at 19.27.01.png" alt=""><figcaption></figcaption></figure>

For example, if you have a KPI threshold equal to **100**, you can set its variable as **key="KPI\_THRESHOLD"** and **value=100** here and reuse it everywhere else as **ENV\_KPI\_THRESHOLD**.

<div>

<figure><img src="../.gitbook/assets/Screenshot 2022-12-09 at 19.27.54.png" alt=""><figcaption><p>Using environment variables in API Calls</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Screenshot 2022-12-09 at 19.29.13.png" alt=""><figcaption><p>Using environment variables in Conditions or Aggregators</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Screenshot 2022-12-09 at 19.28.37.png" alt=""><figcaption><p>Using environment variables in Queries</p></figcaption></figure>

</div>

Then if you want to make it **110** instead of **100**, you can do it in one place, instead of changing all of your workflows and metrics.
