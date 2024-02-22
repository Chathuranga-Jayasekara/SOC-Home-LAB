# 🔨 Wazuh configuration

What we have to do here is, add the agent to the Wazuh server. As you can see in the dashboard there is no any agents at the movement.

{% hint style="info" %}
The Wazuh agent runs on Linux, Windows, macOS, Solaris, AIX, and other operating systems. It can be deployed to laptops, desktops, servers, cloud instances, containers, or virtual machines. The agent helps to protect your system by providing threat prevention, detection, and response capabilities
{% endhint %}

<figure><img src="../.gitbook/assets/image (41).png" alt="" width="563"><figcaption><p>Wazuh Dashboard</p></figcaption></figure>

In order to install the agent click add agent and follow the steps.

In our example we are going to add the windows 10 client to Wazuh. follow the step numbers.

<figure><img src="../.gitbook/assets/image (42).png" alt="" width="563"><figcaption><p>Wazuh Agent Creation</p></figcaption></figure>

Next, you have to assign a name for the agent. this is optional. I have added a name.

<figure><img src="../.gitbook/assets/image (43).png" alt="" width="563"><figcaption><p>Wazuh Agnet Name</p></figcaption></figure>

Then you can copy the entire command in the step number 4.

<figure><img src="../.gitbook/assets/image (44).png" alt="" width="563"><figcaption><p>Wazuh Agent Script</p></figcaption></figure>

Once you copy that, go to your windows 10 PC and open **PowerShell** run as administrator and past the command and then press Enter

<figure><img src="../.gitbook/assets/image (45).png" alt="" width="563"><figcaption><p>Wazuh Agnet script on Win 10 VM</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (47).png" alt="" width="563"><figcaption><p>Installing the Wazuh Agent</p></figcaption></figure>

after that we can start the Wazuh service. in the same PowerShell window type,

```powershell
net start wazuhsvc
```

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption><p>Wazuh Agent Service Started</p></figcaption></figure>

Now move back to the Wazuh dashboard and check whether you have got the agent reported like below.

<figure><img src="../.gitbook/assets/image (49).png" alt="" width="563"><figcaption><p>Wazuh Agent on Dashboard</p></figcaption></figure>

You can click the home button and go to the home menu.

Once you are there, you can check the security events on your windows 10 client.

<figure><img src="../.gitbook/assets/image (50).png" alt="" width="563"><figcaption><p>Wazuh Security Events</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (51).png" alt="" width="563"><figcaption><p>Wazuh Security Events Dashboard</p></figcaption></figure>

