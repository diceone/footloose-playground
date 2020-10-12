#### This is a footloose playground.

## What is footloose?
https://github.com/weaveworks/footloose

This repo uses centos7 modified image for development.

Just download the repo. Then:


```console

$ cd os-examples/centos7/

$ footloose create
INFO[0000] Pulling image: diceone/centos7:0.1.4  ...
INFO[0007] Creating machine: node0 ...
INFO[0008] Creating machine: node1 ...
INFO[0008] Creating machine: node2 ...

$ footloose ssh root@node0.vogeler.dev
```

You can edit the footloose.yaml to increase the cluster size of the containers. 

But there is more...

There is a dir called multi_env

Here you will find a POC for a dev env. 

This dev env consists of a code-Server, node0, jenkins server (more to come)


