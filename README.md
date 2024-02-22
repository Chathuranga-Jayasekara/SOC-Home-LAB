# 💻 Pre Requestees

To setup our lab we need to have some sort of pre requirements. If you are planning to setup this lab on your own computer you must at least have 16GB of RAM and 100GB of disk space.

In this demo I will setup entire lab on my laptop. If you are using an Apple silicon you can use cloud option other wise you will be face some difficulties.

{% hint style="info" %}
You can try VMware Fusion or Parallels
{% endhint %}

I have already installed the Oracle VM VirtualBox in my laptop. For this lab setup we need,

1. Ubuntu VM
2. Windows 10 or 11 VM

You can downlaod the above images form below links.

{% embed url="https://ubuntu.com/download/desktop" %}
Download Ubuntu
{% endembed %}

{% embed url="https://www.microsoft.com/software-download/windows11" %}
Download Windows 11
{% endembed %}

I have already installed the Ubuntu on Oracle VM box.

<figure><img src=".gitbook/assets/image (35).png" alt="" width="563"><figcaption><p>Installing Ubuntu</p></figcaption></figure>

Also I have installed the Windows 10 VM for this lab.

<figure><img src=".gitbook/assets/image (36).png" alt="" width="563"><figcaption><p>Installing Windows 10</p></figcaption></figure>

For the windows 10 VM we have to download and install the windows **Sysmon.**

{% embed url="https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon" %}
Download Sysmon
{% endembed %}

Also we need to have to download the Sysmon config file from the GitHub.

{% embed url="https://github.com/olafhartong/sysmon-modular" %}
Sysmon Config file
{% endembed %}

Install the Sysmon in the windows 10 VM along with the configuration file which has downloaded above.

```powershell
.\Sysmon64.exe -i .\sysmonconfig.xml
```

<figure><img src=".gitbook/assets/image (34).png" alt="" width="563"><figcaption><p>Install Sysmon</p></figcaption></figure>

After installing the Sysmon, you can check Sysmon under the windows event log.

Event Viewer -> Application and Services Logs -> Microsoft -> Windows -> Sysmon

<figure><img src=".gitbook/assets/image (33).png" alt="" width="563"><figcaption><p>Sysmon in Windows Event Viewer</p></figcaption></figure>

After successfully completing all of the above steps will start to install the Wazuh.

{% hint style="info" %}
You have to configure the nextwork connectivity in between these two VMs.  I have added both VMs in Internal network call soc and used same subnet.
{% endhint %}
