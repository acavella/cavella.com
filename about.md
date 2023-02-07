---
title: About
header: About
description: a little bit about
permalink: /about
layout: default
---
<h1 class="display-6">About</h1>

<p class="h5 pt-3">System Setup</p>
<div class="container text-left">
  <div class="row">
    <div class="col-6">
    <ul class="list-group">
        <li class="list-group-item list-group-item-dark fw-bold">Desktop (Custom)</li>
        <li class="list-group-item"><strong>CPU:</strong> AMD Ryzen™ 7 5800X</li>
        <li class="list-group-item"><strong>GPU:</strong> Sapphire Radeon RX 6700 XT</li>
        <li class="list-group-item"><strong>Mem:</strong> Corsair Vengeance Pro 64GB (4x16GB)</li> 
        <li class="list-group-item">
          <div class="d-flex w-100 justify-content-between">
            <strong>Storage:</strong>
          </div>
          <p class="mb-1 ms-2">Crucial P5 Plus Gaming 1TB NVMe</p>
          <p class="mb-1 ms-2">Crucial P5 Plus Gaming 512GB NVMe</p>
          <p class="mb-1 ms-2">Crucial MX500 2TB 3D NAND SATA 2.5-inch SSD</p>
        </li> 
        <li class="list-group-item">
          <div class="d-flex w-100 justify-content-between">
            <strong>Peripherals:</strong>
          </div>
          <p class="mb-1 ms-2">Corsair K70 RGB Mk.2 Keyboard</p>
          <p class="mb-1 ms-2">Corsair Nightsword RGB Mouse</p>
          <p class="mb-1 ms-2">2x Yubikey 5 NFC </p>
        </li> 
        <li class="list-group-item">
          <div class="d-flex w-100 justify-content-between">
            <strong>Software:</strong>
          </div>
          <p class="mb-1 ms-2"><strong>Primary OS: </strong>Windows 11 Pro</p>
          <p class="mb-1 ms-2"><strong>Secondary VM: </strong>Fedora Workstation 37 (Budgie)</p>
        </li>     
    </ul>
    </div>
    <div class="col-6">
    <ul class="list-group">
        <li class="list-group-item list-group-item-dark fw-bold">Laptop (Dell XPS 13 7390)</li>
        <li class="list-group-item"><strong>CPU:</strong> Intel® Core™ i7-10710U</li>
        <li class="list-group-item"><strong>GPU:</strong> Integrated</li>
        <li class="list-group-item"><strong>Mem:</strong> 16GB</li> 
        <li class="list-group-item"><strong>Storage:</strong> Crucial P3 Plus 2TB PCIe Gen4 NVMe</li> 
        <li class="list-group-item">
          <div class="d-flex w-100 justify-content-between">
            <strong>Peripherals:</strong>
          </div>
          <p class="mb-1 ms-2">Yubikey 5C NFC</p>
        </li>    
        <li class="list-group-item">
          <div class="d-flex w-100 justify-content-between">
            <strong>Software:</strong>
          </div>
          <p class="mb-1 ms-2"><strong>Primary OS: </strong>Fedora Workstation 37 (Budgie)</p>
          <p class="mb-1 ms-2"><strong>Secondary VM: </strong>Windows 11 Pro</p>
        </li>  
    </ul>
    </div>
  </div>
</div>

<p class="h5 pt-3">Homelab</p>
<div class="container text-left">
  <div class="row">
    <div class="col-4"><p class="lead">
    I'm currently working on building what I hope one day will be the ultimate Raspberry Pi based homelab. Trying to stay current and relevant in the IT field is incredibly important and a homelab is key to this in my mind. The homelab allows you to practice and maintain your current skills, while giving you opportunties to try new things that you wouldn't always get a chance to do at work.
    </p>
    <p>
    In its current iteration the lab consists of 8 Raspberry Pi 4's. The first four are running Fedora Server 37 and Podman, each independently build around specific key services. InternetPi hosts internet facing services; WireguardVPN, PSI FileTransfer, and . MonitorPi consists of an entire monitoring suite for the lab based on Grafana, Prometheus, Grafana Loki, Rsyslog and Uptime-Kuma. UtilityPi consists of blah blah and blah. And finally PrivacyPi is dedicated as a Wireguard VPN server.
    </p>
    <p>
    The next four (4) Pis are running the latest Ubuntu Server 22.10 configured as a Docker Swarm. This system doesn't have any dedicated workload, but serves to test various workloads in a cluster. Projects are constantly being rotated in and out of the Swarm.
    </p>
    </div>
    <div class="col-8">
      <img src="/assets/images/homelab_diag_v1.png" class="img-fluid" alt="Current Homelab Diagram">
    </div>
  </div>
</div>

### This Site
This website is built with Jekyll, a static site generator, hosted for free using [Github](https://github.com/) and [Netlify](https://www.netlify.com/). I built this site using [Bootstrap v5.3](https://getbootstrap.com/) and with the intent of achieving a lightweight, clean design. This is a constant work in progress, source for this website can be found on my Github.