---
published: false
layout: post
title: Automating WD MyCloud Backups to Backblaze
description: I decided I needed to take a more serious approach to data storage and ultimately data backup.
date: 2021-01-10
---

Recently I decided I needed to take a more serious approach to data storage and ultimately data backup. In the past I've been, what can I say, careless with my data. Bulk storage has been completed on various USB hard drives and critical files have been backed up directly to the cloud (Google, OneDrive). I will say, this strategy has served me well enough for years, however, in the event of a major situation where I needed to recover everything, I can't imagine it would be an easy task. 

## The NAS
When looking at different NAS solutions, I decided to stay in the sub $500 range.  All of these options are ARM based NAS with between 2 and 4 drives.  The biggest difference between them is the web-gui which and what prebuilt apps come with the NAS.  If you look at the higherend options, you'll see apps for using your NAS as a Plex server or Docker host.  None of these features were important to me, essentially I found myself looking for a NAS that supported 1Gbps networking, with as few additional options as possible.  The fewer additional features, the cheaper the bare enclosure cost, leaving more money for the important piece; large, reliable hard disks.

I ultimately settled on the Western Digital (WD) MyCloud EX2 Ultra.  This ARM based NAS can support two (2) 3.5" hard drives in RAID-1. For them I chose two (2) 12 terrabyte WD Red NAS Pro hard drives. As with most people (I assume) the biggest item I backup is my photo collections. I am not a Youtube content creator, I don't have 100s of terrabytes worth of videos, etc..

## Automated Backups to Backblaze B2
Setting up automated backups isn't very difficult, but requires some familiarity with the *nix command line and concepts.  We will use a utility called `rclone` to manage our connection to our Backblaze B2 bucket, handle our initial full disk backup and scheduled incremental updates.  

### Backblaze B2
I'm not going to go into much detail here, as managing your Backblaze account is outside the scope of this article.  Once you have a Backblaze account you'll need to create a new Application Key to use with rclone.  Make sure to copy the keyID and applicationKey from your newly generated App Key, this will be the only time you can retrieve these values.

### Configure rclone on WD MyCloud
```
cd /mnt/HD/HD_a2/Nas_Prog/

wget --no-check-certificate https://downloads.rclone.org/rclone-current-linux-arm-v7.zip

unzip rclone-current-linux-arm-v7.zip

rm rclone-current-linux-arm-v7.zip

ln -s /mnt/HD/HD_a2/Nas_Prog/rclone-<version>-linux-arm-v7/rclone /bin/rclone
```

```
cd /bin/rclone

./rclone config
```

```
