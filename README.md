<img src="img/pull-tab.svg" width="100" />

# opencola-alpha 1.3.3
_updated 9/21/2023_


Welcome to the [OpenCola](https://opencola.io) alpha. We look forward to hearing your feedback and getting help ironing out the wrinkles. While a lot of the foundation is complete, we will continually be working on adding new features and making it easier to install / use. Some key things that we will be working on:

1. **Mobile Apps**: We are currently working on a mobile app in Flutter that will support both iOS and Android devices. 
2. **UI Design**: The current UI desing is intentionally mininmalistic, meant to show the overall functionality in a simple way. We will work with an actual designer to develop a proper "feel" to the application.   
3. **Data Importers**: Since most people have a lot of content on existing sites, we will implement importers to make it easy to import activity into OpenCola.

Feel free to add issues you come across to [issues](https://github.com/johnmidgley/opencola-alpha/issues) for this repo (preferred) or email dev@opencola.io. If you have questions, please use the [discussions](https://github.com/johnmidgley/opencola-alpha/discussions) area, so that others can benefit from the answers. 

You're also welcome to share this alpha with friends, but we are limited on the amount of support we can provide, so we will prioritize those on the alpha list.


# New in version 1.3.3

* Cleaned up setup and login UI
* Embedded help into application
* Added instruction on empty pages
* Embeded Chrome Extension into application

# New in version 1.3.2

Fixed issues with display of attachments

# New in version 1.3.1

This release brings some important features and imrpovements as well as a number of minor bug fixes.


## File attachments

You can now added arbitrary file attachments to posts, allowing you to share pdf documents, images and more.

## Cleaned up UI

* Image treatment is now more promininet, giving your feed a more traditional feed look. 
* Creating / editing posts has been simplified
* Comments are now done in a markdown wysiwyg editor.  

## Standardized Serialization 

The original storage serialization formats were custom for maximum size efficiency. These formats have now been moved to protobuf, improving future interoperability and extendability.

> NOTE if you're upgrading: Since the transaction data format has changed, your transaction chain needs to be re-generated and re-signed. When you start OpenCola, your data will be automatically migrated. You will temporarily lose access to your peer data, because it is incompatible with the new format. Once your peers upgrade, their data will automatically re-synchronize. 

## Re-write of Relay Server Protocol

The new relay server protocol use protobuf messages, includes a number of efficiency improvements, and now supports store and forward functionality, so that you can receive peer updates even when they are not online

## New in Older Versions
[New in version 1.2.0](1.2.0-release-notes.md)

# Installation
OpenCola runs a small server on your computer. You use OpenCola through a your web browser just like a web app or service except you're connecting to the OpenCola server software on your machine.

## Server

- [MacOS](docs/macOS/install.md)
- [Windows](docs/windows/install.md)
- [Linux](docs/linux/install.md)
- [Docker Based](docs/docker/install.md)

# Setting Up

Setup instruction are now inside the application iteself. Just start the application and follow the instructions. Help on how to use OpenCola can also be found inside the application itself. 

