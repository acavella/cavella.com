---
layout: post
title: Ansible Role Wireguard
description: Yesterday I completed and published my first official Ansible Role.
date: 2021-12-10
category: Homelab
thumbnail: "/assets/images/gradiant_placeholder.svg"
---

Yesterday I completed and published my first official Ansible Role. Much of the motivation for this project came from the great work [Jeff Geerling](https://github.com/geerlingguy) is doing around Ansible. If you are interested in getting started with Ansible, I highly suggest checking out his Ansible 101 series.  

The purpose of this role is to install Wireguard on Linux. The role includes OS specific tasks that should allow it to work on any system.  The role installs a simple server and generates the keys for a single client user. It has been tested on Debian, Ubuntu, CentOS and Fedora.  

[Github Source](https://github.com/acavella/ansible-role-wireguard)  
[Ansible Galaxy](https://galaxy.ansible.com/acavella/wireguard)

<figure>
  <img alt="Github Profile" src="/assets/images/role-wg.jpg" />
  <figcaption>Fig.1 - Wireguard Role on Ansible Galaxy</figcaption>
</figure>