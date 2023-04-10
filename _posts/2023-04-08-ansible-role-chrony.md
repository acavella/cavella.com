---
share: true
links:
  mdlinks: true
  convert: true
  internal: true
filename: 2023-04-08-ansible-role-chrony
layout: post
title: "New Ansible Role, Chrony"
date: 2023-04-08
category: Development
thumbnail: "/assets/images/clock_thumb.jpg"
---

As part of my day job my team and I have been working on building out an Infrastructure-as-Code framework and implementation. The end goal being able to spin-up and deploy our custom mobility gateways on the fly and customize to meet individual customer requirements easily. As part of this I have been building a number of Ansible Roles that can be plugged in to customize base images/installs. Some of these roles are very specific and would serve nobody outside of individual project. However, some of these roles are very standard services that others may find useful. I will publish these more standard Roles and hopefully you can find some benefit from them.

The first I have published is a simple Ansible Role to configure a chrony daemon. The roles leverages a variable file found in `./defaults/main.yml` to set various options, peers/pools/servers, is the environment isolated, etc... 

- Github: [Ansible Role: Chrony](https://github.com/acavella/ansible-role-chrony)
- Ansible Galaxy [Ansible Role: Chrony](https://galaxy.ansible.com/acavella/chrony)
