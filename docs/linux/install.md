<img src="../../img/pull-tab.svg" width="100" />

# Installing OpenCola on Linux

1. <strong>Download</strong> the [Linux Release](https://github.com/johnmidgley/opencola-alpha/releases/download/v1.3.2/OpenCola-Linux-1.3.2.tgz)
2. In a terminal, untar it wherever you like:
```
> tar -xzf OpenCola-Linux-1.3.2.tgz
```
3. Start OpenCola
```
> opencola/bin/opencola 1>/dev/null 2>/dev/null &
```        
4. A browser window will open. Follow the instructions on the page for installing an SSL certificate. (Certificates will be placed in ```~/.opencola/storage/cert```)


> If you'd like to view the logs, open a terminal and run:
> ```
> tail -f ~/logs/opencola/opencola-server.log
> ```

Back to: [Setting Up](../../README.md#setting-up)
