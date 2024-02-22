---
description: >-
  Wazuh is a free and open source security platform that unifies XDR and SIEM
  protection for endpoints and cloud workloads.
---

# ⌚ Wazuh Installation

<figure><img src=".gitbook/assets/image (31).png" alt=""><figcaption><p>Wazuh</p></figcaption></figure>

We are going to install the wazuh on the ubuntu VM. Ubuntu VM is going to be our server and Windows 10 VM will be our client.

Wazuh installation is simple. Open the Terminal in ubuntu VM and past this command and press enter. ( Depending on your account you might required the super user privileges.)

```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

<figure><img src=".gitbook/assets/image (32).png" alt="" width="563"><figcaption><p>Installing Wazuh</p></figcaption></figure>

Once the installation been completed please make sure to take the note of the Wazuh **admin** credentials.

<figure><img src=".gitbook/assets/image (37).png" alt="" width="563"><figcaption><p>Wazuh admin credentails.</p></figcaption></figure>

{% hint style="info" %}
Please keep these admin credentials someware safe. Because you need this to login to Wazuh dashboard later.
{% endhint %}

If all set, you can browse your local host IP, means your VM host IP and log in to the Wazuh dashboard with above saved credentials.&#x20;

In my example Wazuh IP is 192.168.200.200

<figure><img src=".gitbook/assets/image (38).png" alt="" width="563"><figcaption><p>Wazuh Dashboard</p></figcaption></figure>
