<img src="../img/pull-tab.svg" width="100" />

# Setting up ZeroTier
<br/>
In order to use ZeroTier, you must create an account, set up a network, and run the client on any devices that are running or would like to access OpenCola.

To create an account, go to [ZeroTier](https://www.zerotier.com/) and sign up. Once signed, up, navigate to your [networks](https://my.zerotier.com/network), which should look something like:
<img src="img/zt-create-network.png" width="800" />

Click "Create A Network". A network with a random name will be created, something like:
<img src="img/zt-network-created.png" width="800" />

Click on the network to edit it. While there are many settings on the page, you can just use the defaults. It is helpful to give the network a meaningful name (e.g. opencola):
<img src="img/zt-edit-network.png" width="800" />

Take note of the network id (in this case, 632ea290854c7435). For each device you would like to add to the network, [download](https://www.zerotier.com/download/) and install the client. Once installed, you need to join the network. To do this, open ZeroTier on your device and add your network:
- On Mac, click the ZeroTier icon in your menu bar, "Open Control Panel", and enter the network id in the box beside "Join Network" at the bottom.
- On iOS, open the app, click + at the top right, Accept the terms and then enter the NetworkId

Other OSs we haven't tried yet, but the process will be similar.

Once your devices have been added, return to the network and scroll to the "Members" section and check the "Auth?" box beside the addresses you've added.

 <img src="img/zt-edit-members.png" width="800" />

Each device will now have an additional ip address assigned, which will be in the range set for the network (scroll to IPv4 Auto-Assign in the network config):

<img src="img/zt-ip-address.png" width="800" />

Go to go the machine running opencola (that you should have installed ZeroTier on) and restart the server. If you check the logs, there will you'll notice new access urls that with a new ip address. You can use these addresses to access OpenCola from anywhere. The VPN is private and secure (traffic is encrypted), so you can use http if you like, or https to be extra safe. If you decide to use https, make sure to regenerate new certificates (that will include the ZeroTier ip address), as described next.
