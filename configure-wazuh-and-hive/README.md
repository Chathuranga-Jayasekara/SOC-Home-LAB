# ⚙ Configure Wazuh and Hive

After doing all of these, our next step is to configure hive and the Wazuh. As a first step let start the configuration of the hive.

First will focus on the Cassandra which is database of the hive. to do the configuration of the Cassandra navigate to the following.

```bash
/etc/cassandra/cassandra.yaml
```

First Change the Cassandra Cluster name.

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="563"><figcaption><p>Cassandra Cluster Name</p></figcaption></figure>

Next change the listen address from [localhost](http://localhost/) to your hive address. in my example that is 192.168.200.200

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="563"><figcaption><p>Cassandra Listen Address</p></figcaption></figure>

Now change the rpc\_address. Replace the [localhost](http://localhost/) with your hive IP address same as the above listen\_address- In my case 192.168.200.200

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption><p>Cassandra rpc_address</p></figcaption></figure>

Next change the seed address. but please remember do not change the port number **7000**.

<figure><img src="../.gitbook/assets/image (20).png" alt="" width="563"><figcaption><p>Cassandra Seeds Port</p></figcaption></figure>

Then stop the cassandra service.

```bash
systemctl stop cassandra.service
```

After that you can remove the older files which is in the Cassandra by using the below command.

```bash
sudo rm -rf /var/lib/cassandra/*
```

Now you can start the Cassandra service using this command

```bash
systemctl start cassandra.service
```

To make sure whether the Cassandra service is running or not, you can use the below command.

```bash
systemctl start cassandra.service
```

As you can see the service is running after our changes.

<figure><img src="../.gitbook/assets/image (21).png" alt="" width="563"><figcaption><p>Cassandra service is active and running</p></figcaption></figure>

The next thing we have to configure is Elasticsearch. the purpose of the Elasticsearch is querying the data. you can find the config file of the Elasticsearch under,

```bash
/etc/elasticseach/elasticsearch.yml
```

What you have to do is, find the cluster name and rename it as you want. in my example I'm changing my cluster name in to “ thehive”

<figure><img src="../.gitbook/assets/image (22).png" alt="" width="563"><figcaption><p>Elasticsearch Cluster Name</p></figcaption></figure>

Also uncomment the [node.name](http://node.name/) and leave it as node-1

<figure><img src="../.gitbook/assets/image (23).png" alt="" width="563"><figcaption><p>Elasticsearch Node Name</p></figcaption></figure>

When you scrolling down you will see the **network.host** IP address. uncomment that and added your hive IP address. in my case IP address was 192.168.200.200

<figure><img src="../.gitbook/assets/image (24).png" alt="" width="563"><figcaption><p>Elasticsearch Network Host IP</p></figcaption></figure>

In Elasticsearch by default http port is 9200. if you want you can uncomment that and enable the port and use customer port number. I'm going to uncomment that and enable that but using the same port.

<figure><img src="../.gitbook/assets/image (25).png" alt="" width="563"><figcaption><p>Elasticsearch http port</p></figcaption></figure>

In order to start the Elasticsearch, it will need the discovery seed or cluster initial master node. In my case I'm going to uncomment the initial master node like below. and please keep remember to remove the node 2 because we don't have a node-2 at this stage. if you are planning to setup or you are setting up a node-2 you can keep it as it is.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>Elasticsearch Master Nodes</p></figcaption></figure>

Now save all the configurations and go ahead and **start** the Elasticsearch service by using below command.

```bash
systemctl start elasticseach
```

<figure><img src="../.gitbook/assets/image (27).png" alt="" width="563"><figcaption><p>Elasticsearch Start</p></figcaption></figure>

Once this is done, we can enable the service using below command

```bash
systemctl enable elasticsearch
```

<figure><img src="../.gitbook/assets/image (28).png" alt="" width="563"><figcaption><p>Elasticsearch service enable</p></figcaption></figure>

To make sure the service you can run this command.

```bash
systemctl status elasticseach
```

As you can see it is active and running..

<figure><img src="../.gitbook/assets/image (29).png" alt="" width="563"><figcaption><p>Elasticsearch service running</p></figcaption></figure>

{% hint style="info" %}
Once you have done that please make a note to double check that Cassandra service as well. some times that service may hanged or stopped.
{% endhint %}

```bash
systemctl status cassandra.service
```

<figure><img src="../.gitbook/assets/image (30).png" alt="" width="563"><figcaption><p>Cassandra Service is Running</p></figcaption></figure>

