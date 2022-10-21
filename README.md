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

At this point, a TLS certificate has been generated so that you can use OpenCola over https. Enter 'y' to install the certificate. This requires sudo access, so you will have to enter your system password on the command line, and once again in a UI dialog for the key tool.

```
y
~/.opencola/storage/cert ~/dev/opencola/install/unix
Password:
~/dev/opencola/install/unix
Server started - visit http://localhost:5795
                   or https://localhost:5796 (Secure - recommended)
```

The application is started and you can navigate to https://localhost:5796. (You can use plain http link too, but it is not secure). When you navigate to the page, you'll be prompted to set a password:

<img src="img/setPassword.png" width="800" />

Enter a password and confim it. You will then be prompted to enter a username and your password to continue. The user name can be anything you like, but so you don't forget it, you must set it in the config file (storage/opencola-server.yaml) and is used for web authentication. Once your password is set, you'll be prompted to login to the app. Using the default username 'oc' the page looks like:

<img src="img/startApp.png" width="800" />

Lastly, you will need to authenticate your browser:

<img src="img/browserAuthenticate.png" width="800" />

Now OpenCola is ready for use.



