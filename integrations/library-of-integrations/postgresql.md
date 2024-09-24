# PostgreSQL

**Integration type**: `Read` `Write` `SQL`

Integration with PostgreSQL allows you to read and write data from and to PostgreSQL instances in a streaming mode.&#x20;

**Data for the connection:**

<figure><img src="../../.gitbook/assets/Screenshot 2024-04-23 at 16.42.51.png" alt=""><figcaption></figcaption></figure>

## Using SSH connection for open-source and on-premise editions

If you want to connect to your PostgreSQL database while using our open-source and on-premise edition, you need to place your public RSA SSH key called `id_rsa.pub` to the following two folder:

* `processor/taskrunner/config/keys/`
* `backend/integrations/config/keys/`

&#x20;If you don't have RSA SSH keys yes, here you can learn how to [generate them](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key).&#x20;
