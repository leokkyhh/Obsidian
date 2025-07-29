# 1. Prerequisite
Host: Ensure you have a public IP by checking from your client with ping [your_host_public_ip]. Or use [ping](https://dnschecker.org/ping-ipv4.php).
Otherwise, install [Tailscale](https://tailscale.com) or set up a VPN server to connect both your client and host under the same network.

# 2. Set up your port forwarding
Go to your WiFi router administrator website or app, and set port 3389 forwarding to your host IP. You can check your host IP by running `ipconfig`; it should start with 192.168. Set forwarding for both TCP & UDP connections.

# 3. Turn on RDP permission on Windows

Open Settings -> System -> Remote Desktop. Turn on `Remote Desktop` and `Network Identification`. Make sure you are an administrator; otherwise, you need to add your current user to the `RemoteDesktopUser` group.

# 4. Connect from client

To start from a Windows client, open cmd and run `mstsc`, then enter your public IPv4 address or Tailscale address and username. It is not recommended to use an online Microsoft account on your host Windows; it is a mess.

On Linux, install `xfce4` and `xrdp`. It is recommended to use KDE desktop for a smoother connection. Refer to this [link](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/use-remote-desktop?tabs=azure-cli).
```
sudo apt update && sudo apt upgrade -y
sudo apt install -y kde-plasma-desktop
sudo apt install -y xrdp
```
```
echo "/usr/bin/startplasma-x11" > ~/.xsession
cat <<EOF > ~/.xsessionrc
export XDG_SESSION_DESKTOP=KDE
export XDG_DATA_DIRS=/usr/share/plasma:/usr/local/share:/usr/share:/var/lib/snapd/desktop
export XDG_CONFIG_DIRS=/etc/xdg/xdg-plasma:/etc/xdg:/usr/share/kubuntu-default-settings/kf5-settings
EOF
sudo sed -i 's/^new_cursors=true/new_cursors=false/g' /etc/xrdp/xrdp.ini
```
```
sudo systemctl enable xrdp
sudo systemctl start xrdp
And you should be all done.
```
