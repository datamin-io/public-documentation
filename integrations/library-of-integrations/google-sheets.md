# Google Sheets

**Integration type**:  `Write`

Integration with Google Sheets allows you to stream data from any data source to spreadsheets in real-time.&#x20;

**Data for the connection:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-23 at 18.53.19.png" alt=""><figcaption></figcaption></figure>

## Setting up integration

### Step 1. Creating a service account with JSON credentials

1. In the Google Cloud console, [go to the Service accounts](https://console.cloud.google.com/iam-admin/serviceaccounts?walkthrough\_id=iam--create-service-account-keys\&start\_index=1#step\_index=1).
2. Select a project.
3. Create a new service account or select an existing one.

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 18.57.06.png" alt=""><figcaption></figcaption></figure>

Steps 2 and 3 are optional and are not needed if you want to make basic Ylem's integration work. As soon as the service account is created, create a key with JSON credentials for it:

1. Click the email address of the service account that you want to create a key for.
2. Click the **Keys** tab.
3. Click the **Add key** drop-down menu, then select **Create new key**.
4. Select **JSON** as the Key type and click **Create**.

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 18.58.34.png" alt=""><figcaption></figcaption></figure>

Clicking **Create** downloads a service account key file. After you download the key file, you cannot download it again.

### Step 2. Enable Google Sheets API

Go to [https://console.developers.google.com/apis/api/sheets.googleapis.com/overview](https://console.developers.google.com/apis/api/sheets.googleapis.com/overview), select the project, and confirm enabling Google Sheets API.

### Step 3. Create Google Sheet and grant access to it to the service account

Go to the Google Sheet you want to stream data to, click on File -> Share -> Share with others, and share it with the service account you just created.

<div>

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.00.38.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.00.02.png" alt=""><figcaption></figcaption></figure>

</div>

### Step 4. Create an integration

Now you can create an integration in Ylem by adding JSON credentials, Spreadsheet ID, and Sheet ID. The last two parameters you can get from the URL of the spreadsheet you just created:



<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.07.51.png" alt=""><figcaption><p>Spreadsheet Id</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.08.02.png" alt=""><figcaption><p>Sheet Id</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.08.30.png" alt=""><figcaption></figcaption></figure>

### Step 5. Create a test pipeline and stream data

Now you can create a pipeline and run it to stream data to the new spreadsheet:

<div>

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.11.46.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.12.24.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.12.07.png" alt=""><figcaption></figcaption></figure>

</div>

If you run the pipeline now, the new content should appear in the spreadsheet:

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-26 at 21.14.16.png" alt=""><figcaption></figcaption></figure>
