---
layout: post
title: Automating WD MyCloud Backups to Backblaze B2
description: I decided I needed to take a more serious approach to data storage and ultimately data backup.
date: 2022-01-6
category: Homelab
thumbnail: "/assets/images/gradiant_placeholder.svg"
---

Recently I decided I needed to take a more serious approach to data storage and ultimately data backup. In the past I've been, what can I say, careless with my data. Bulk storage has been completed on various USB hard drives and critical files have been backed up directly to the cloud (Google, OneDrive). I will say, this strategy has served me well enough for years, however, in the event of a major situation where I needed to recover everything, I can't imagine it would be an easy task. 

### The NAS
When looking at different NAS solutions, I decided to stay in the sub $500 range.  All of these options are ARM based NAS with between 2 and 4 drives.  The biggest difference between them is the web-gui which and what prebuilt apps come with the NAS.  If you look at the higherend options, you'll see apps for using your NAS as a Plex server or Docker host.  None of these features were important to me, essentially I found myself looking for a NAS that supported 1Gbps networking, with as few additional options as possible.  The fewer additional features, the cheaper the bare enclosure cost, leaving more money for the important piece; large, reliable hard disks.

I ultimately settled on the Western Digital (WD) MyCloud EX2 Ultra.  This ARM based NAS can support two (2) 3.5" hard drives in RAID-1. For them I chose two (2) 12 terrabyte WD Red NAS Pro hard drives. As with most people (I assume) the biggest item I backup is my photo collections. I am not a Youtube content creator, I don't have 100s of terrabytes worth of videos, etc..

### Automated Backups to Backblaze B2
Setting up automated backups isn't very difficult, but requires some familiarity with the *nix command line and concepts.  We will use a utility called `rclone` to manage our connection to our Backblaze B2 bucket, handle our initial full disk backup and scheduled incremental updates.  

#### Backblaze B2
I'm not going to go into much detail here, as managing your Backblaze account is outside the scope of this article.  Once you have a Backblaze account you'll need to create a new Application Key to use with rclone.  Make sure to copy the keyID and applicationKey from your newly generated App Key, this will be the only time you can retrieve these values.

#### Install rclone on WD MyCloud
```
cd /mnt/HD/HD_a2/Nas_Prog/

wget --no-check-certificate https://downloads.rclone.org/rclone-current-linux-arm-v7.zip

unzip rclone-current-linux-arm-v7.zip

rm rclone-current-linux-arm-v7.zip

ln -s /mnt/HD/HD_a2/Nas_Prog/rclone-<version>-linux-arm-v7/rclone /bin/rclone
```
#### Configure rclone for Backblaze B2
The following steps show the steps to configure the remote connection to B2 using rclone, create a new remote bucket and generate your initial remote backup.

```
cd /bin/rclone

./rclone config

No remotes found - make a new one
n) New remote
q) Quit config
n/q> n
name> remote
Type of storage to configure.
Choose a number from below, or type in your own value
[snip]
XX / Backblaze B2
   \ "b2"
[snip]
Storage> b2
Account ID or Application Key ID
account> 123456789abc
Application Key
key> 0123456789abcdef0123456789abcdef0123456789
Endpoint for the service - leave blank normally.
endpoint>
Remote config
--------------------
[remote]
account = 123456789abc
key = 0123456789abcdef0123456789abcdef0123456789
endpoint =
--------------------
y) Yes this is OK
e) Edit this remote
d) Delete this remote
y/e/d> y
```
View all buckets on the remote:
```
./rclone lsd remote
```
Create a new bucket:
```
./rclone mkdir remote:bucket0
```
List the contents of a bucket:
```
./rclone ls remote:bucket0
```
Perform the initial backup to your new remote bucket:
```
./rclone sync -i /mnt/HD/HD_a2/share/ remote:bucket
```
#### Automating future incremental backups
We can automate future backups using a cronjob.  It's as simple as adding the backup command we ran above to the systems crontab.  The example below configures a backup to run every Saturday at 1 AM.
```
crontab -e 

0 1 * * 6 /bin/rclone/rclone sync -i /mnt/HD/HD_a2/share/ remote:bucket
```
