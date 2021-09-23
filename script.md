# SCRIPT

## Introduction

Lors d'un jug précédent on avait parlé de wasm
-> clone
-> faut faire un setup
-> quid de nvm

=> cela serait bien d'avoir un environnement prêt d'un simple clic

C'est ce que propose gitpod.

Deux façon de le lancer. On va le lancer sur wasm :
https://gitpod.io/#https://bitbucket.org/stefdev49/wasm/src/live/

Ou le bouton gitpod via extension du navigateur

On voit l'environnement, c'est pas mal comme début :
- on a un vs code dans un cloud
- avec un shell linux complet et fonctionnel
- sudo apt install vim
- docker ps

Ce sont les fichiers sous /workspace qui sont sauvegardés.

Limites matérielles ? Rien vu dans les docs:
- htop
- ulimit -a

Good catch! JAVA_TOOL_OPTIONS is indeed set based on GITPOD_MEMORY.

This 1.88 GB value is the current memory request (a Kubernetes concept), i.e. how much memory we expect Gitpod workspaces to typically use.

However, all Gitpod workspaces are allowed to use up to 12.88 GB (the current memory limit) before any safeguard mechanism kicks in. (If your workspace uses more than 12.88 GB, the Linux OOM-killer will start killing your top-RAM-consuming processes until your workspace goes below 12.88 GB again.)

Faisons un tour du dashboard

pin -> garde pour toujours au lieu d'être supprimé si trop vieux
download/delete/share
## GITPODIFICATION

Mais allons plus loin, automatisons l'environnement:

gp init

puis on bouge tout ce qui vient du makefile et du script dans le .gitpod.yml

pour prendre en compte git push puis réouverture avec gitpod

Plus besoin de :

.PHONY: clean configure

configure:
	setup/emcc.sh
	mkdir -p out
	npm install

=> settings en bas

ajout extension avec bouton
sinon en éditant

git lens

démo env variable
gp en
gp sync-await coucou
=> split

préinit avec before mais requiert un hook


client lourd => image de base nouvelle

config nvm

partage : 
- par snapshot
- par partage de workspace live