---
description: The Hive is A 4-IN-1 SECURITY INCIDENT RESPONSE PLATFORM
---

# 🐝 The Hive Installation



<figure><img src=".gitbook/assets/image (39).png" alt=""><figcaption><p>The Hive</p></figcaption></figure>

After Installing the Wazuh we can start installation of the hive. The hive is free and opensource security incident response platform. In my case I will install the hive also in the same VM which we have installed the Wazuh.

{% hint style="info" %}
There are few dependencies before we install the hive. Which are,\
Install Java

Install Cassandra

Install Elasticsearch
{% endhint %}

Here are more details about how to install each components before we install the hive.

```bash
Install Java

wget -qO- https://apt.corretto.aws/corretto.key | sudo gpg --dearmor  -o /usr/share/keyrings/corretto.gpg
echo "deb [signed-by=/usr/share/keyrings/corretto.gpg] https://apt.corretto.aws stable main" |  sudo tee -a /etc/apt/sources.list.d/corretto.sources.list
sudo apt update
sudo apt install java-common java-11-amazon-corretto-jdk
echo JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto" | sudo tee -a /etc/environment 
export JAVA_HOME="/usr/lib/jvm/java-11-amazon-corretto"
```

```bash
Install Cassandra

wget -qO -  https://downloads.apache.org/cassandra/KEYS | sudo gpg --dearmor  -o /usr/share/keyrings/cassandra-archive.gpg
echo "deb [signed-by=/usr/share/keyrings/cassandra-archive.gpg] https://debian.cassandra.apache.org 40x main" |  sudo tee -a /etc/apt/sources.list.d/cassandra.sources.list
sudo apt update
sudo apt install cassandra
```

```bash
Install ElasticSearch

wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch |  sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
sudo apt-get install apt-transport-https
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/7.x/apt stable main" |  sudo tee /etc/apt/sources.list.d/elastic-7.x.list
sudo apt update
sudo apt install elasticsearch
```



After completing the above dependencies you can continue installtion of the hive using below commands.

```bash
Install TheHive

wget -O- https://archives.strangebee.com/keys/strangebee.gpg | sudo gpg --dearmor -o /usr/share/keyrings/strangebee-archive-keyring.gpg
echo 'deb [signed-by=/usr/share/keyrings/strangebee-archive-keyring.gpg] https://deb.strangebee.com thehive-5.2 main' | sudo tee -a /etc/apt/sources.list.d/strangebee.list
sudo apt-get update
sudo apt-get install -y thehive
```

<figure><img src=".gitbook/assets/image (40).png" alt="" width="563"><figcaption><p>Installing the hive</p></figcaption></figure>

{% hint style="info" %}
Default Credentials on port 9000 \
credentials are '<mark style="color:red;">**admin@thehive.local**</mark>' with a password of '<mark style="color:red;">**secret**</mark>'
{% endhint %}
