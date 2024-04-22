# Connecting Hubspot

HubSpot is a software platform designed to help your company market and sell more effectively (CRM, ROI).\
\
Instructions are available as the video or in text below.

{% embed url="https://youtu.be/BXkJbxm4gbQ" %}
How to integrate Datamin with Hubspot
{% endembed %}

### How to connect?

First, you'd need to go to the list of your [destinations](https://app.datamin.io/destinations), click "Add destination" and select Hubspot.\
\
If you do it the first time and you don't have any authorization yet, so you will see such form:

<figure><img src="../../.gitbook/assets/hubspot/hubspot_destination_no_auth.png" alt=""><figcaption></figcaption></figure>

So first things first — the authorization.

### Authorize your Hubspot

Go to "[Hubspot Authorizations](https://app.datamin.io/hubspot-authorizations)" and click "Add Hubspot Authorization". You will be redirected to Hubspot's page where you need to give your concern.

<figure><img src="../../.gitbook/assets/hubspot/hubspot_consent_auth.png" alt=""><figcaption></figcaption></figure>

Once consent's given, you will be redirected back to our application, where you can change the name of just a freshly connected Hubspot's instance of yours.

<figure><img src="../../.gitbook/assets/hubspot/hubspot_connected.png" alt=""><figcaption></figcaption></figure>

### Configure your new destination

Now, on the page of new Hubspot destination creation, you can choose your just-connected Hubspot. Now the question is, what are those pipeline IDs, pipeline stage ID, and owner ID? These are the internal ids in your Hubspot. How to find them?

#### Pipeline / stage id

First of all navigate yourself to the configuration of pipelines, by clicking that link on the Tickets page.

<figure><img src="../../.gitbook/assets/hubspot/hubspot_link_to_edit_pipelines.png" alt=""><figcaption></figcaption></figure>

In there you will find a list of your pipelines and corresponding stages. By clicking \</>, it will reveal an ID, that you will need to put in your destination configuration.

#### Owner id

An owner is the one who creates a ticket. E.g, you could create a special account for just Datamin or use any other natural person account. In order to find the owner id, please go to the ticket properties, find a property "Ticket Owner", and click "Edit".\
\
You'll see something like this.

<figure><img src="../../.gitbook/assets/hubspot/hubspot_owner_id.png" alt=""><figcaption></figcaption></figure>

You need to copy a value in the red rectangle.

### Example of the configured destination

After you've done all steps above, your Hubspot configuration in Datamin's will look like this. Now you can use it in your workflows!

<figure><img src="../../.gitbook/assets/hubspot/hubspot_done.png" alt=""><figcaption></figcaption></figure>
