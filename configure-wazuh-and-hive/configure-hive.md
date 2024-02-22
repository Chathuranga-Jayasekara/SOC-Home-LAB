# 🔧 Configure Hive

Before we stat the configurations of the hive we want to make sure that hive user and group has access to certain file path.

```bash
ls -la /opt/thp
```

<figure><img src="../.gitbook/assets/image (7).png" alt="" width="563"><figcaption><p>Hive file path</p></figcaption></figure>

As we can see now root has access to the hive directory. we need to change that. In order to change that you can use below command

```bash
chown -R thehive:thehive /opt/thp
```

Then you can use the above command again to verify the status.

```bash
ls -la /opt/thp
```

<figure><img src="../.gitbook/assets/image (8).png" alt="" width="563"><figcaption><p>Hive file path permission change</p></figcaption></figure>

Now we are good to go for configure the hive configuration files.

The hive configuration files located under the,

```bash
/etc/thehive/application.conf
```

Use below command to edit the configuration file.

```bash
gedit /etc/thehive/application.conf
```

<figure><img src="../.gitbook/assets/image (9).png" alt="" width="563"><figcaption><p>The hive config file</p></figcaption></figure>

When you scroll down you can find the database and index configurations. This is what we need to configure. We have to remove the default **host** name **IP** and add the hive VM IP.&#x20;

Here I have replace the 127.0.0.1 in to my IP 192.168.200.200.

<figure><img src="../.gitbook/assets/image (10).png" alt="" width="563"><figcaption><p>Hive Hostname IP</p></figcaption></figure>

Also you have to change the Cassandra cluster name here as well as the host name under the index search below. please make sure to add the same cluster name as we configured in Cassandra cluster.

<figure><img src="../.gitbook/assets/image (11).png" alt="" width="563"><figcaption><p>The Hive Cluster Name</p></figcaption></figure>

Then you scroll down you can find the application based URL which is pointing to the local host. I'll change it to my usual IP of the VM 192.168.200.200

<figure><img src="../.gitbook/assets/image (12).png" alt="" width="563"><figcaption><p>The Hive Application Base URL</p></figcaption></figure>

That’s all… now we have to save the configuration file and exit from the text editor.

Now we can start the hive as well as the enable the hive.

```bash
systemctl start thehive
systemctl enable thehive
```

<figure><img src="../.gitbook/assets/image (13).png" alt="" width="563"><figcaption><p>Hive service enable</p></figcaption></figure>

Now lets go and check the service status of the hive.

```bash
systemctl status thehive
```

As you can see it is active and running

<figure><img src="../.gitbook/assets/image (14).png" alt="" width="563"><figcaption><p>Thehive Service is Active and Running</p></figcaption></figure>

{% hint style="info" %}
NOTE - If you cannot access the hive please make sure check all the service

Cassandra, Elasticsearch and hive without all of them the hive won’t start.
{% endhint %}

If all good then we can try to access the hive web interface using the IP address and the port number. in my case 192.168.200.200:9000

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="563"><figcaption><p>The Hive Login Page</p></figcaption></figure>

{% hint style="info" %}
We can use the default credentials to log in to the hive

<mark style="color:red;">username- admin@thehive.local</mark>

<mark style="color:red;">password - secret</mark>
{% endhint %}

<figure><img src="../.gitbook/assets/image (16).png" alt="" width="563"><figcaption><p>The Hive Logins</p></figcaption></figure>

Now we have  done with the hive configuration and will move to the Wazuh and configure that.
