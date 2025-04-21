#deploy #stage #compose #docker #rus

## Server Setup Guide

### Docker

To run the server locally, you must have Docker installed. We highly recommend using [Docker Desktop](https://www.docker.com/products/docker-desktop/) as it provides a user-friendly UI for managing containers.

### Make

You will also need the **Make** utility installed. It allows you to use predefined commands for server management, making the process faster and more efficient.

Linux
```bash
sudo apt update && sudo apt install make  # Ubuntu/Debian
sudo dnf install make                     # Fedora
sudo pacman -S make                       # Arch Linux
```

macOS

```bash
xcode-select --install
```

Windows
```bash
choco install make
```

To check the installation result, run this command

```bash
make --version
```

### Deployment

The next step is to download the server manifests and configs. You can find the repository with the files we need [here](https://github.com/QuizWars-Ecosystem/deployment). Or run the following command (recommended).

```bash
git clone https://github.com/QuizWars-Ecosystem/deployment
```

To run this command, you'll need to have the _git_ utility installed.

Now your local machine has everything we need for full server operation.

### Start

To launch the server, the Docker Engine must be active. Start the Docker Desktop application we installed earlier.

Now navigate to the cloned _deployment_ repository so your console's working directory is at the repository's root folder.

In the repository root, you'll find the _Makefile_ we need.

![[Screenshot 2025-04-21 204948.png]]

In it you will find all the commands that we will use to manage the server state.

Here you can see the contents of this file.

> [!warning] Attantion !
> This file may have changed a lot by now. Don't copy commands from this document, take them from the current file in the repository.


```bash
# STAGING Docker compose commands  
stage-up:  
    make stage-gateway-up stage-users-up
  
stage-down:  
    make stage-users-down stage-gateway-down  
  
stage-gateway-up:  
    docker-compose -f ./compose/stage/api-gateway.docker-compose.yaml --env-file=./compose/stage/configs/gateway.env up -d --build  
  
stage-gateway-down:  
    docker-compose -f ./compose/stage/api-gateway.docker-compose.yaml --env-file=./compose/stage/configs/gateway.env down  
  
stage-users-up:  
    docker-compose -f ./compose/stage/users-service.docker-compose.yaml --env-file=./compose/stage/configs/users.env up -d --build  
  
stage-users-down:  
    docker-compose -f ./compose/stage/users-service.docker-compose.yaml --env-file=./compose/stage/configs/users.env down  
```

Further we will often resort to commands from this file, as they help us to call already predefined commands in an abbreviated form. Let's quickly see how to call them.

To call any command from the available ones, we just need to write the name of the utility *make* and the alias of the command we need to the open console.

Let's say we want to call the command *stage-up* that we already have in our file. To do this, just write the following in the console.

```bash
make stage-up
```

And you will immediately see the result of this command.

> [!danger] Attantion
>In this tutorial and the following actions we will use only those commands that have the prefix **stage-** since these commands are based on working in the STAGE environment. You may get an undesirable result caused by other commands.
> 

### Commands

Next, we'll quickly go over how to launch all required programs in the local environment using the knowledge mentioned above.

I recommend executing all subsequent commands directly in the console. If you use IDE tools to run these commands, their behavior and results may differ.

##### Stage commands

- **stage-up** – This command is designed to launch the API [[API-Gateway (ENG)]], all services, and their additional dependencies in one go. As a result, you'll get a fully prepared and operational server ready to handle your requests.
- **stage-down** – This command does the opposite of the previous one. It will shut down the entire server in the correct order.
- **stage-gateway-up** – This command will start the request proxy program and also launch its required component, _Consul_.
- **stage-gateway-down** – This command will gracefully stop all incoming requests to the server and terminate its operation.
- **stage-{SERVICE_NAME}-up/down** – Commands following this pattern are intended to start and stop the service specified in the command itself. Note that some services may take longer to start or stop than others, as they may have pending tasks or require additional dependencies, such as a database.

> [!danger] Warning!  
> Every provided service must receive requests exclusively through the [[API-Gateway (ENG)]]. Therefore, always ensure this program is running and correctly forwarding requests to the services.

### Manifests

Docker Compose manifests are files that describe a container or a group of containers that can be launched directly in Docker using the _docker-compose_ command. We follow the same approach, so we'll use it for local environment work.

In our repository in the folder *compose/stage* (now you see it on the screenshot)
![[Screenshot 2025-04-21 212317.png]]

You'll find everything we'll be using here - specifically, the _docker-compose_ manifests and configuration files for the programs. These exact manifests are used in the _Makefile_ we described earlier.

Let's open one of them and examine its contents.

We've selected _users-service.docker-compose.yaml_. We won't delve into all the intricacies of writing such a file, but will only cover the parts relevant to us.

> [!warning] Attention!  
> Everything you see and read below may already differ from the current version of the file.

#### Users-Service

> [!note] Note  
> Note that the _yaml_ file format follows a _key: value_ structure. It's also important to understand that this format is highly sensitive to indentation. To avoid errors, we recommend not editing anything until you're comfortable with this format. Additionally, I suggest installing a plugin that will highlight potential errors in your manifest.


![[Screenshot 2025-04-21 2134.png]]

Let's analyze this section in more detail:

1. _services:_ - This directive declares that what follows is a list of containers in this manifest.
2. _users-service:_ - This is the container name in this file. It's important to understand that if you don't specifically specify the _container-name:_ directive, Docker will automatically assign a suffix to the container name when launched. Typically this is just a number. Example: _users-service-1_.
3. _image:_ - One of the most fundamental container directives. It contains the repository name from which Docker will pull a ready-built image of your program if it's not available locally. In our case, this is an image stored in the Docker registry. After the name you can see a tag - in our case it's the _latest_ tag, indicating we're using the most recent version of the image.
4. _volumes:_ - This manifest directive allows us to mount files or folders into the container. Here we're mounting our program's configuration file inside the container so it can be read from within.
5. _networks:_ - Lists all internal networks that enable containers within Docker to communicate with each other simply through their names and ports.
6. _depends_on:_ - Makes our container dependent on another one under certain conditions. In our case, Docker will only start our program when the _users-postgres_ container has launched and announced it's ready to accept connections.

In the next section, we'll examine directives we haven't covered yet.

![[Screenshot 2025-04-21 2153.png]]

1. _environment:_ - allows us to assign values to predefined environment variables. In our case, we're redefining variables for _POSTGRES_USER_, _POSTGRES_PASSWORD_, and _POSTGRES_DB_.

> [!warning] Environment variables and their usage  
> As I mentioned, nearly everything we use requires configuration. In _stage_ environment we use two approaches: _env_ files and _yaml_, though occasionally you might encounter other formats (rarely).
> 
> How does this work exactly?
> 
> In this same folder you can find a _configs_ directory containing files with variables. Now we'll examine the simplest and most essential format for us.
> 
> Such files end with _.env_
> 
> _Contents of users.env_
> ```env
> # Service configs  
> GRPC_PORT: 21001  
> USERS_DB_USERNAME: user  
> USERS_DB_PASSWORD: pass  
> USERS_DB_NAME: users  
> USERS_DB_PORT: 15432  
> ``` 
> 
> Here we can find the same variable names as in the manifest. These variables contain the values we define. To pass these variables into the manifest context, we use the following approach:
> 
> ```bash
> docker-compose ... --env-file=./compose/stage/configs/gateway.env `
> ```
> The _--env-file=..._ flag allows us to inject the variables file directly into the manifest that Docker will execute.
> 
> You can try modifying some variables and restarting the manifest. Try changing the program's port and you'll see the changes take effect without errors.

2. _restart:_ - a directive that lets us specify conditions under which Docker will automatically restart our container. In our case, it will do so if the _users-postgres_ container crashes with an error.
3. _ports:_ - a directive describing the container's port list. It's important to understand that if you don't see this directive, you won't be able to access your containerized program externally. Only other containers _in the same network_ can communicate with it. If you want to make requests to the container, expose the port. Also note the syntax matters. The entry 8080:8080 means Docker will forward all requests to your machine's port 8080 to the container's port 8080, which in turn goes to the internal program also listening on port 8080. Your program must be listening on this port internally.

With this, we can conclude our lesson on running the server locally and the basics of docker-compose manifests.