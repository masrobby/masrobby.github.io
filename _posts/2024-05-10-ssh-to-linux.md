---
layout: post
title: Simple guide on how to SSH into a Linux server
date: 2024-05-10 10:35:00
tags: ssh into linux
categories: guide
featured: true
---

Here's a simple guide on how to SSH into a Linux server:

## Step 1: Open a Terminal
On your local machine, whether it's running Linux, macOS, or Windows (using a tool like PuTTY), open a terminal or command prompt.

## Step 2: Use the SSH Command
Once you have the terminal open, use the ssh command followed by the username and the IP address or domain name of the server you want to connect to. The basic syntax is:

```bash
ssh username@server_ip_or_domain
```

For example:

```bash
ssh ssh john@example.com
```

If the server uses a non-standard SSH port (not the default port 22), you can specify it with the -p flag followed by the port number. For example:

```bash
ssh -p 2222 john@example.com
```

## Step 3: Enter Your Password (If Required)
If this is your first time connecting to the server from your local machine, you may be prompted to confirm the server's fingerprint. Once confirmed, you'll then be prompted to enter the password for the username you provided. Note that when typing your password, you won't see any characters on the screen.

## Step 4: Confirm Successful Connection
Once you've entered the correct password, you should be logged into the server via SSH. You'll see a command prompt indicating that you're now interacting with the server remotely.

## Step 5: Perform Tasks on the Server
Now that you're connected, you can perform various tasks on the server just like you would if you were physically sitting in front of it. You can navigate the file system, edit files, install software, and more.

## Step 6: Exiting the SSH Session
To exit the SSH session and return to your local machine's command prompt, simply type:

```bash
exit
```

And press Enter. This will close the connection to the server.

That's it! You've successfully SSH'd into a Linux server. Remember to always keep your server credentials secure and avoid sharing them with unauthorized individuals.
