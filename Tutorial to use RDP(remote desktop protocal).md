# 1. Prerequisite
 Host: Ensure you has a public IP checking by ping from your client `ping [your host ip]`
Or here [ping](https://dnschecker.org/ping-ipv4.php)
Else install [tailscale](https://tailscale.com) or set up an VPN server which connect both your client and host under same network.

# 2. Set up your port fowarding
By enter to your Wifi router administrator website or apps, set port 3389 forwarding to your host ip. You can check by `ipconfig`, it should start by 192.168. On both TCP&UDP connection.

# 3. Turn on RDP permission on Win

Open setting -> System -> Remote Desktop. Turn on `remtoe desktop` and `network identification`. Make sure you are administrator else you need to add your current user on `RemoteDesktopUser` down below.

# 4. Connect from client

To start from client Window by cmd `mstsc`, type in your pulic ipv4 address or tailscale address and user name. Not reccomand to use online ms account on your host’win, it is a MESS.

 On linux, install `xfce4` and `xrdp`, recommend to use kde desktop for smoother connection. Refer this [link](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli)
And you should be all done.
