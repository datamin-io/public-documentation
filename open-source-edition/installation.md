# Installation

The open-source edition of **Ylem** can be installed with pre-build containers from the **Ylem installer**:

{% embed url="https://github.com/ylem-co/ylem-installer" %}

Or can be downloaded from GitHub or built from source:

{% embed url="https://github.com/ylem-co/ylem" %}

## Installation

### Option 1. Install from pre-build containers

The best way to install Ylem is to clone the repository [https://github.com/ylem-co/ylem-installer](https://github.com/ylem-co/ylem-installer) and follow the installation instructions from it. It will install Ylem from the latest version of pre-build containers stored on Docker Hub.

Ylem will be available at [http://localhost:7331/](http://localhost:7331/)

### Option 2. Build and install from the source

If you want to compile Ylem from the source, run `docker compose up` or `docker compose up -d` from this repository. It will compile the code and run all the necessary containers.

Ylem is available at [http://127.0.0.1:7330/](http://127.0.0.1:7330/)

⚠️ Please pay attention. Compiling from the source might take some time and will keep the resources of your machine busy.

#### **To rebuild a particular container**

If you want to rebuild a particular container from a source locally, run the following:

```
docker compose build --no-cache %%CONTAINER_NAME%%
```

E.g.

```
docker compose build --no-cache ylem_users
```

## Using your own Apache Kafka cluster

Ylem uses Apache Kafka to exchange messages for processing pipelines and tasks. By default Ylem already comes with the pre-configured Apache Kafka container, however, you might already have an Apache Kafka cluster in your infrastructure and might want to reuse it.

In this case, you need to take the steps described [here](https://docs.ylem.co/open-source-edition/usage-of-apache-kafka).

## Configuring environment variables in .env files

Some particular integrations might require extra steps and using `.env` files. Configure them if you need to.

The list of such integrations and more information about them is in [our documentation](https://docs.ylem.co/open-source-edition/configuring-integrations-with-.env-variables).\
