# Overview

This project provisions a simple 3 node cluster with Docker installed.  The Rancher node contains the install for Rancher.  After provisioning, go to `http://192.168.56.101:8080` to access Rancher console.

# Requirements

1) Vagrant
2) VirtualBox

# Instructions

1) Clone directory to local machine
2) Open terminal and navigate to cloned directory
3) Run `vagrant up`
4) After provisioning go to `http://192.168.56.101:8080` to access Rancher console

# Adding Hosts to Cluster

When prompted to add hosts to cluster from Rancher console access the nodes by opening terminal and going to cloned directory and running `vagrant ssh node1` or `vagrant ssh node2`

# Action Items

- Refactor Vagrant script and provision nodes with a loop