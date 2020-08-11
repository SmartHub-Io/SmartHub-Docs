---
description: ''
sidebar: 'docs'
prev: '/docs/endpoints/'
next: '/docs/how-to-create-a-plugin/'
---

# How to contribute

When contributing to this repository, please first discuss the change you wish to make via an issue, or any other method with the owners of this repository before making a change.  
If you find any spelling mistakes or have improvements to offer, we are open to anyone who has ideas and wants to contribute to this project.

To develop on your local machine and contribute to any project, just follow the steps for the respective project.  

Note we have a code of conduct, please follow it in all your interactions with the project.

## Pull Request Process

> __The PR process applies to all repositories !!__

1. Ensure the code is up to date and be sure that the code follows the clean code guidelines and all pipeline checkarks are __green__.
2. Update the README and/ or documentation(SmartHub-Docs) with details of the changes. (if needed)
3. Your pull request will be reviewed by the team and if everything is fine it will get merged.

## SmartHub

Follow these steps if you want to contribute to the __SmartHub__ project

### Installation

1. Docker
    - Download and install docker for your OS [Link](https://docs.docker.com/)
2. .Net core
    - Download and install .net core sdk for your OS [Link](https://dotnet.microsoft.com/download)
3. Ef core tool
    - Install Entity Framework core tool globally. Insert following command into your terminal:
    `dotnet tool install --global dotnet-ef`
    to update the tool
    `dotnet tool update --global dotnet-ef`
4. Clone Repository
    - `git clone https://github.com/SmartHub-Io/SmartHub.git`
5. Build and create database
    - Go to "SmartHub.Api/"
        - Type into terminal `dotnet restore` and `dotnet build`
    - Go to "SmartHub.Ui/"
        - Type into terminal `npm install`
    - Go to "SmartHub.Api/"
        - Type into terminal `dotnet ef database update`

### Run

1. Run `docker-compose up` from the folder
    - Run `dotnet ef database update`. Only run this on DB changes or during the first time
2. Run `dotnet run Use_Staticfiles_DEV=false Pgsql_User=<your name> Pgsql_pwd=<your pwd>` from "SmartHub.Api" folder
    - Or in your IDE run the "SmartHub.Api--Args" project Task from "launchSetting.json".
3. Run `npm run serve` from the "SmartHub.Ui/" folder
4. Open your browser and go to "localhost:8080" (UI), "localhost:5000/swagger"(swagger)

__Pgsql_User__ => the user you gave to your docker postgres container \
__Pgsql_pwd__ => the pwd you gave to your docker postgres container
__Use_Staticfiles_DEV__ => indicates wheter the pogramm uses a proxy to the seperated started Ui or servers the Ui as static files (default is "false")
> Running the programm without these args will cause errors at the moment !!!

### Database Ui
For a nice postgresql-ui a pgadmin container is also started, go to [Link](http://localhost:5050) and type in the credentials from the compose file.
If you don't like that you can of course still connect any other tool with the database.

## SmartHub-Docs

Follow these steps if you want to contribute to the __Smarthub-Docs__ project.

### Installation

1. Clone repository
    - `git clone https://github.com/SmartHub-Io/SmartHub-Docs.git`
2. Build and install packages
    - Go to "SmartHub-Docs/"
        - Type into terminal `npm install`

### Run
Jist go to the root directory and type into the terminal  `npm run dev`.

## SmartHub-Plugins

Follow these steps if you want to contribute to the __Smarthub-Plugins__ project.

### Installation

1. Clone repository
    - `git clone https://github.com/SmartHub-Io/SmartHub-Plugins.git`
2. Build 
    - Go to "SmartHub-Plugins/SmartHub-Plugins/" folder
        - Type into terminal `dotnet resore` and `dotnet build`
        - If no errors appear everything is perfect 😉
