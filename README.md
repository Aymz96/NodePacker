# Nodejs Packer
In this repository, there are files which will be working in conjuntons with the NodeCookbookStarterCode. These will be used to create an Amazon Machine Image (AMI) in AWS. It will consist of npm, pm2, nginx and nodejs.


## Pre-requisites
- In order to run the Nodejs Cookbook you must ensure you have the packages below:

```CSS
- Packer
- AWS Account
- git
- chef
    Chef Workstation:
      - ChefDK version: 4.7.73
      - Chef Infra Client version: 15.7.32
      - Chef InSpec version: 4.18.51
      - Test Kitchen version: 2.3.4
      - Foodcritic version: 16.2.0
      - Cookstyle version: 5.20.0
```


## Packer
- Packer is a tool which is used to create machine images using any configuration management tool. for example in this project we have used Chef and AWS EC2 machines. The images will be configured to the right operating system and softwares needed.

## How to use
Clone and navigate into the nodePacker directory and follow the below steps.
- Run berkshelf to pull the latest nodejs cookbook.
```bash
$ berks vendor
```
- You must configure packer.json to be able to use the AWS details and keys. Also make sure your AWS credentials are saved in your environment variables.

- verify the packer.json file.

```bash
$ packer validate packer.json
```
- If the above validation passes, run the packer.json file.

```bash
$ packer build packer.json
```
- This will open a connection in the AWS and allow it to create an EC2 machine.
