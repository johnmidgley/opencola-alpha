<img src="img/pull-tab.svg" width="200" />

# opencola-alpha

Welcome to the OpenCola alpha.

# Installation

## Prerequisites

Download and install Docker from https://www.docker.com/

<details><summary>Why Docker?</summary>
<br>
<p>
OpenCola currently runs inside a docker container, which provides a few advantages over a direct install:

1. It isolates the application so it can only access it's data folder and communicate on controlled ports (5795 for http and 5796 for https)
2. It isolates system dependencies (i.e. the Java 11 runtime)
3. It allows for a network of isolated services to be deployed (i.e. Tor proxy and router)
4. It makes it easy for OpenCola to be hosted on another computer, if desired.
</p>
</details>

In order to make sure that OpenCola runs at startup / login, set docker to start when you log in:

<img src="img/dockerSettings.png" width="800" />


## Install OpenCola

1. Download the [archive](dist/opencola-alpha.zip)
2. Unarchive it wherever you like (we'll call this location $OPENCOLA)

# Starting OpenCola

Open a terminal and navigate to $OPENCOLA. 

```
cd unix
./start
```

You should see output similar to:

```
Creating storage
No SSL certificate found
[+] Running 2/2
 ⠿ Network opencola_default   Created 0.0s
 ⠿ Container opencola-server  Started 0.3ss
Docker container started
Waiting for certificate creation
New certs have been created. Install (y/n)?
```

If this is the first time you're starting OpenCola, a TLS certificate will have been generated so that you can use OpenCola over https. Enter 'y' to install the certificate. This requires sudo access, so you will have to enter your system password on the command line, and once again in a UI dialog for the key tool.

```
y
~/.opencola/storage/cert ~/dev/opencola/install/unix
Password:
~/dev/opencola/install/unix
Server started - visit http://localhost:5795
                   or https://localhost:5796 (Secure - recommended)
```

You can now navigate to https://localhost:5796. (You can use plain http link too, but it is not secure). The first time you start OpenCola, you'll be prompted to set a password:

<img src="img/setPassword.png" width="800" />

Enter a password and confim it. You will then be prompted to enter a username and your password to continue. The user name can be anything you like, but so you don't forget it, you must set it in the config file (storage/opencola-server.yaml) and is used for web authentication. Once your password is set, you'll be prompted to login to the app. Using the default username 'oc' the page looks like:

<img src="img/startApp.png" width="800" />

Lastly, you will need to authenticate your browser:

<img src="img/browserAuthenticate.png" width="800" />

Now OpenCola is ready to use, and you will see your (empty if this is the first time running) feed:

<img src="img/emptyFeed.png" width="800" />

# Setting up Your User

You can set a display name and image for yourself in peer settings by clicking the <img src="img/peers.png" width="15" /> icon:

<img src="img/setInfo.png" width="800" />

Fields:

| Field | Description |
| --- | --- |
| <img src="img/peers.png" width="15" /> | Name visible to peers when you connect (more later) |
| <img src="img/id.png" width="15" /> | Your gobally unique OpenCola user id - not changeable |
| <img src="img/key.png" width="15" /> | A cryptogrpahic public key used to encrypt and sign data - not changeable yet |
| <img src="img/link.png" width="15" /> | The address at which peers can request data from you. Default is to use the OpencCola relay server (more later) |
| <img src="img/photo.png" width="15" /> | Url of image for your picture. This has to be a web link right now. |
| <img src="img/refresh.png" width="15" /> | Whether or not the user is actively being sychronized with (more later) |

# The Browser Extenion

## Installing the Extension

OpenCola comes with a browser extension. It currenlty only works with Chrome based browsers (e.g. Chrome, Chromium, Brave, Edge). We will provide other extnsions in the future. To install the extension, go to your browsers extensions page. In Brave, navigate to brave://extensions, which looks like:

<img src="img/manageExtensions.png" width="800" />

In the future, we will provide the extension in the Web Store, but for now you must install it manually. To do so, click the "Developer mode" slider: 

<img src="img/enableDeveloperMode.png" width="800" />

Then click "Load Unpacked" and select the folder $OPENCOLA/chrome. 

<img src="img/openColaExtensionEnabled.png" width="800" />

Lastly, pin the extension to your toolbar (so it's always visible) by clicking the extension icon (the puzzle piece) and click the pin beside OpenCola:

<img src="img/pinExtension.png" width="800" />

## Using the Extension

To use the extension, simply click the OpenCola icon in the toolbar:

<img src="img/extensionToolbar.png" width="800" />

The various icons mean:

| Icon | Description |
| --- | --- |
| <img src="img/save.png" width="15" /> | Save the current page |
| <img src="img/like.png" width="15" /> | Like the current page |
| <img src="img/trust.png" width="15" /> | Trust the current page | 





