on créé le projet puis on clique directement sur gitpod
on se loggue avec son compe (ici bitbucket)

https://www.gitpod.io/docs/getting-started

pour initialiser :

gp init

On commit puis on ferme, enfin on relance et on voit tout s'intaller et la preview s'ouvrir

gitpod /workspace/gitpod $ cat /etc/os-release 
NAME="Ubuntu"
VERSION="20.04.2 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.2 LTS"
VERSION_ID="20.04"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=focal
UBUNTU_CODENAME=focal


Quand on lance on voit bien les ports 8000 et 35279 (livereload), quand on clique on en voit la liste
- preview bloqué dans firefox mais marche dans chrome ..... 

- activation du live reload: gp url

Puis on installe une extension => .gitpod.yml => config marche pas dans ff, mais bien dans chrome

Introducing the Gitpod Local Companion app

extension navigateur

extensions vscode

installation package net-tools

token replace
npm install --save-dev gulp-token-replace
=> on a bien une génération avec la varible env injectée et la page qui se met à jour

		<!-- ne marche pas, il faut le port complet !-->
		<!--mais là encore pb ... il faut rendre le port public ? on évite websocket et on indique le port 443!-->

https://www.gitpod.io/docs/languages/javascript/

ultimage guide
https://www.gitpod.io/blog/gitpodify

settings -> keymap

"editor.fontSize": 16
# Présentation gitpod

## projet wasm

blah blah

## Début

### Concept
At the heart of the Gitpod concept is the notion that maintaining a developer machine is hard work and can be fragile, especially for coders who work with more than one SDK. A Gitpod workspace is ephemeral, with its configuration defined in code. There are trade-offs such as a startup delay, the limitations of working remotely, and the cost of a subscriptions, against benefits such as a predictable developer environment customised for each project, and the ability to work anywhere with a wide range of PCs or tablets as the client.


glisser/ déposer marche !

## Extensions

### VS code

image

## Similaires

https://github.com/features/codespaces

eclipse / che

## VRAC

https://github.com/apps/gitpod-io

Introducing the Gitpod Local Companion app

As of today, you can access your Gitpod workspace from your local environment 🎉!

Why does this matter? Imagine you start a development server for your web application in Gitpod. You can preview that online at a https://nnnn-x.y.gitpod.io URL, where “nnnn” is the port your dev server listens on. Sometimes though, development features such as live reloading may not be compatible with that URL format and rather require something like http://localhost:10000 to communicate with the dev server.

With the Gitpod Local Companion app, localhost URLs can now access your dev server running in a Gitpod workspace. The best part of that: It works with any TCP port. You could run a MySQL database in your Gitpod workspace and access the database with your favourite GUI through localhost:3306.

To learn more and get started today, please see our introduction blog post.

[local is going remote](https://www.gitpod.io/blog/local-app)

```bash
curl -OL https://gitpod.io/static/bin/gitpod-local-companion-linux
chmod +x ./gitpod-local-companion-*
```

### A la maison

Prerequisites

As we at Gitpod follow a “Saas First” strategy we have a very limited set of platforms that we support.

You still might get Gitpod to run on other platforms (especially with the help of our awesome community) but there will be no support from Gitpod for those efforts.

Requirements regarding the Kubernetes the cluster:

    Workspace nodes require Ubuntu = 18.04 as Host OS at the moment

    Gitpod should work on small Kubernetes nodes out of the box (2vCPUs, 8GB RAM). For a better experience we recommend at least 4vCPUs and 16GB RAM for workspaces nodes. For cost efficiency, we recommend to enable cluster-autoscaling.

You need the following “local” tools to follow this guide:

    kubectl with connection to your cluster

    helm in version >= 3.