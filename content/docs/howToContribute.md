---
description: ''
sidebar: 'docs'
prev: '/docs/endpoints/'
next: '/docs/how-to-create-a-plugin/'
---

# How to contribute

When contributing to this repository, please first discuss the change you wish to make via an issue, or any other method with the owners of this repository before making a change.  
If you find any spelling mistakes or have improvements to offer, we are open to anyone who has ideas and wants to contribute to this project.

To develop on your local machine and contribute to any repository _([SmartHub](https://github.com/SmartHub-Io/SmartHub), 
[SmartHub-Docs](https://github.com/SmartHub-Io/SmartHub-Docs), [SmartHub-Plugins](https://github.com/SmartHub-Io/SmartHub-Plugins))_, 
just follow the steps below for the respective one.  

Note we have a code of conduct, please follow it in all your interactions with the project.

## Pull Request Process

> __The PR process applies to all repositories !!__

1. Ensure the code is up to date, that the code follows the clean code guidelines __and__ all required pipelines are passed.
2. Update the README and/ or documentation(SmartHub-Docs) with details of the changes. (if needed)
3. Your pull request will be reviewed by the team and if everything is fine it will get merged.

## SmartHub

Follow these steps if you want to contribute to the __SmartHub__ project

### Installation

1. Docker
    - Download and install docker for your OS [Link](https://docs.docker.com/)
2. .Net core
    - Download and install .net core sdk for your OS [Link](https://dotnet.microsoft.com/download)
    - Project currently at 3.1.3
3. Ef core tool
    - Install Entity Framework core tool globally. Insert following command into your terminal:
    `dotnet tool install --global dotnet-ef`  
    - To update it type into a terminal `dotnet tool update --global dotnet-ef`
4. Clone Repository
    - `git clone https://github.com/SmartHub-Io/SmartHub.git`
5. Build and create database
    - Go to "SmartHub.Api/"
        - Type into a terminal `dotnet restore` then `dotnet build`
    - Go to "SmartHub.Ui/"
        - Type into a terminal `npm install`
    - Go to "SmartHub.Api/"
        - Type into a terminal `docker-compose up` or `docker-compose up -d` (so you don't need to open a new terminal)
        - Then type into a terminal `dotnet ef database update`

### Run

1. Run `docker-compose up` from the "SmartHub.Api/" folder. _(starting database)_
2. Run `dotnet run Use_Staticfiles_DEV=false Pgsql_User=<your name> Pgsql_pwd=<your pwd>` from "SmartHub.Api" folder.
    - Or in your IDE run the "SmartHub.Api--Args" project Task from "launchSetting.json". _(starting backend)_
3. If _Use_Staticfiles_DEV=true_ you don't need to run `npm run serve` from the "SmartHub.Ui/" folder, because the Ui is being served from the backend. _(starting frontend)_
4. Open your browser and go to "localhost:8080" (UI) or "localhost:5000/swagger"(swagger).

__Pgsql_User__ => the username which is set in the docker-compose.override.yml file (__default__ == postgres)  
__Pgsql_pwd__ => the pwd which is set in the docker-compose.override.yml file (__default__ == 1234)  
    -> Edit these in the docker.compose.override.yml file  
__Use_Staticfiles_DEV__ => indicates whether the program uses a proxy to the separated started Ui or servers the Ui as static files (default is "false")
> Be aware running the program without these args will cause errors at the moment !!!

### Database Ui
For a nice postgresql-ui a pgadmin container is started aswell, go to [Link](http://localhost:5050) and type in the credentials from the docker-compose.yml file. 
(__default__ = pgadmin4@pgadmin.org and admin)  
If you don't like that you can of course remove that service from the docker-compose file and/ or connect any other tool with the database.

## SmartHub-Docs

Follow these steps if you want to contribute to the __Smarthub-Docs__ project.

### Installation

1. Clone repository
    - `git clone https://github.com/SmartHub-Io/SmartHub-Docs.git`
2. Build and install packages
    - Go to the root directory
        - Type into a terminal `npm install`

### Run
Just go to the root directory and type into a terminal  `npm run dev`.

## SmartHub-Plugins

Follow these steps if you want to contribute to the __Smarthub-Plugins__ project.  
You can only make sure all plugins can be build, you can't run them directly from this dotnet solution. 
More information on plugins are on the next page.

### Installation

1. Clone repository
    - `git clone https://github.com/SmartHub-Io/SmartHub-Plugins.git`
2. Build 
    - Go to "SmartHub-Plugins/SmartHub-Plugins/" folder
        - Type into terminal `dotnet resore` and `dotnet build`
        - If no errors appear everything is perfect 😉
