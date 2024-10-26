# Installation

The open-source edition of **Ylem** can be installed with pre-build containers from the **Ylem installer**:

{% embed url="https://github.com/ylem-co/ylem-installer" %}

Or can be downloaded from GitHub or built from source:

{% embed url="https://github.com/ylem-co/ylem" %}

## Installation

### 1. Install and configure dependencies

To run Ylem, the following dependencies must be first installed and configured.

#### Docker 4

If you don't yet have Docker 4 installed, [install](https://www.docker.com/products/docker-desktop/) it from their official website for your OS.

#### Apache Kafka

Ylem uses Apache Kafka to process pipelines and tasks. [Install](https://kafka.apache.org/) it from their official website or skip this step if you already have it installed.

We also recommend that you install the Apache Kafka GUI software to manage its topics and subscriptions.

### 2. Create Kafka topics

To be able to work correctly, Ylem requires the following Apache Kafka topics to be created:

* task\_runs
* task\_runs\_load\_balanced
* task\_run\_results
* query\_task\_run\_results
* notification\_task\_run\_results

### 3. Configure environment variables in .env files

Some particular integrations might require extra steps and using `.env` files.

More information is in [our documentation](https://docs.ylem.co/open-source-edition/configuring-integrations-with-.env-variables).

### 4. Install from pre-build containers

The best way to install Ylem is to clone the repository [https://github.com/ylem-co/ylem-installer](https://github.com/ylem-co/ylem-installer) and run&#x20;

`docker compose up`&#x20;

or&#x20;

`docker compose up -d`&#x20;

from it. It will install Ylem from the latest version of pre-build containers stored on Docker Hub.

### Or build and install from the source

If you want to compile Ylem from the source, clone our [main repository](https://github.com/ylem-co/ylem) and run&#x20;

`docker compose up`&#x20;

or&#x20;

`docker compose up -d`&#x20;

from the root folder of it.&#x20;

It will compile the code and run all the necessary containers.
