---
tags: [ "eclipse" , "che" ]
title: Getting Started
excerpt: "Convert any repository into a developer workspace."
layout: docs
permalink: /:categories/getting-started/
---
{% include base.html %}
The Chedir getting started guide will walk you through your first Chedir project, and show the basic features Chedir has to offer.

If you are curious what benefits Chedir has to offer, you should also read the [Why Chedir?]({{base}}/docs/chedir/why/index.html) page.

Before diving into your first workspace, please check how to use the latest version of Chedir, which is also part of the [Eclipse Che CLI]({{base}}/docs/setup/cli/index.html). And since Docker is required for everything related to Che, make sure that is installed as well.


```shell  
# Clone a source code repo that you want to convert into a workspace
git clone https://github.com/che-samples/web-java-spring-petclinic
cd web-java-spring-petclinic

# Convert it into a workspace running in a private Che server
docker run -it --rm <DOCKER_PARAMETERS> eclipse/che-cli:<version> [COMMAND] dir <path-to-web-java-spring-petclinic-folder> up

# Note: Currently requires no other Che servers to be running simultaneously
# New version coming will allow many directories mounted into a single server
```


After running the above commands, you will have a project inside of a workspace inside of a running Che server. The workspace has its own runtime, powered by an Ubuntu Docker image. The project is mounted from the local directory into the workspace and is given full git capabilities.

You can either open the IDE in your browser to work on the project immediately. The Web IDE has a terminal for accessing the Docker image powering the workspace. You can SSH into the workspace by pressing the `SSH` button in the IDE to get connectivity details. You can then make modifications, set the project type in the IDE, use language intellisense, or run a debugger. When you are done making modifications, you can use the IDE to commit and push changes with git, or continue to do those on your command line. You can then stop the workspace and unlink it with `docker run -it --rm <DOCKER_PARAMETERS> eclipse/che-cli:<version> [COMMAND] dir <path-to-project> down`.

Now imagine every repository that you work on being this easy to convert into a debuggable workspace that includes its own pre-configured IDE. Chedir is all you need to convert repositories into workspaces with their own private runtimes, dependencies, networking and synchronized folders.

The rest of this guide will walk you through setting up a more complete project, covering more features of Chedir.
