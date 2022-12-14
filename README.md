# Rex CLI

[![Build](https://github.com/TheWisePigeon/rex/actions/workflows/build.yml/badge.svg)](https://github.com/TheWisePigeon/rex/actions/workflows/build.yml)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/TheWisePigeon/rex/pulls)
[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/TheWisePigeon/rex/graphs/commit-activity)
[![Generic badge](https://img.shields.io/badge/Maintainer-TheWisePigeon-blue.svg)](https://github.com/TheWisePigeon)

## What is Rex?
Rex is a CLI that will help you scaffold your next Express project, using either TypeScript or JavaScript. But Rex can be much more.

The structure of the templates are one that I follow for all my projects. Sticking to that structure improved my productivity and the readability/maintanability of my projects. That's why I decided to make a CLI that will help me bootstrap such projects as quickly as possible. If you intend to follow the same structure as me, then Rex becomes kind of a Framework, since it will now have a little control on how you write your code.

That's why I decided to call it a **Pseudo Framework**

## Usage
### Installation
⚠️Rex is available only on windows for now.

To install Rex on your system, head over to [this link](https://github.com/TheWisePigeon/rex/releases/tag/pre-release) and download the `RexCLI.exe`

Once the installation is complete, you will need to add Rex's folder to your path. Check in the `Program Files` folder, you will find a Rex folder, copy it's path and add it to your Path environment variable.

You should now be ready to use Rex. The usage is quite simple.

## The **init** action
To create a new project with rex, you will use the `init` command

The syntax is `rex init {template} {project_name}`. Some examples below
```bash
rex init js crudAPI
rex init ts hello_rex
```
You can do use "ts"/"js" or "typescript"/"javascript", both will work
```bash
rex init javascript crudAPI
rex init typescript hello_rex
```

### Folder Structure
A rex scaffolded project structure looks like this
![image_2022-12-04_181858118](https://user-images.githubusercontent.com/95161388/205508333-b67a4b77-b1f4-45ae-aed3-0d074cc19d8f.png)

Each folder contain a readme file that gives you information about what the folder should contain.

- The `rex.conf.json` file contains informations that rex reads while doing some operations. Do not edit that file unless you understand what it is doing and know what you are doing.
- The `config` folder must contain a single index file, from where you will export things such as your database url, your app environment...
- The `middlewares` folder contains every middleware that is not a main one. For example, if you would have a middleware that would check if the a request comes from a authenticated user by verifying a jwt, you would write it here and export it.
- The `routes` folder contains folders that stand for routes. These folders contain index files where you export a `Express.Router`. The name of the folder must match the name of the service which must be dealing with a specific ressource or task.
- The `services` folder contains files, where you export services. A service is a middleware that performs a specified task. For example the AuthService.ts is where you would write everything that relates to authentication in your app like signing in, registering, changing passwords... Each service is defined as a function and exported
- The `utils` folder contains utility functions. For example a function to hash passwords, compare a user provided password against a hash stored in the database...every piece of code that is reused but doesn't have a direct relation to the ressource or application business logic

## Adding a new service with Rex
You can quickly create a new service with rex, by running 
```bash
rex add service <service_name>
```
at the root of your rex generated project. This will create a file in the services directory, a folder in the routes directory and an index file in that folder. For design purposes, please make sure the name of your services files always start with a capital letter.

AuthService.ts ✅

authservice.ts ❌

## Roadmap
Here are a few things I will work on for Rex.

- Extend Rex to other technologies by adding more templates
- Let users create their own templates
- Automatic imports when creating a new service

That's it. Drop a star if you like this project or find it useful. Feel free to contribute. If you gpt any remarks, please reach to me through my socials down below

[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:zozozozeph@gmail.com)
[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discordapp.com/users/624747283640221723)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/pigeondev0_0)
