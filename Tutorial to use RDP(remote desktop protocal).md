# 1. Prerequisite
 Host: Ensure you has a public IP checking by ping from your client `ping [your host ip]`
Or here [ping](https://dnschecker.org/ping-ipv4.php)
Else install [tailscale](https://tailscale.com) or set up an VPN server which connect both your client and host under same network.

# 2. Set up your port forwarding
Go to your WiFi router administrator website or app, and set port 3389 forwarding to your host IP. You can check your host IP by running `ipconfig`; it should start with 192.168. Set forwarding for both TCP & UDP connections.

# 3. Turn on RDP permission on Windows

Open Settings -> System -> Remote Desktop. Turn on `Remote Desktop` and `Network Identification`. Make sure you are an administrator; otherwise, you need to add your current user to `RemoteDesktopUser` below.

# 4. Connect from client

To start from a Windows client, open cmd and run `mstsc`, then enter your public IPv4 address or Tailscale address and username. It is not recommended to use an online Microsoft account on your host Windows; it is a mess.

 On linux, install `xfce4` and `xrdp`, recommend to use kde desktop for smoother connection. Refer this [link](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli)
And you should be all done.
