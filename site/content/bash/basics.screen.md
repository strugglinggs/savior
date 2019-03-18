+++
title = "Screen Basics"
date = 2019-02-26T13:03:26-05:00
weight = 4
enableEmoji = true
+++
{{% notice info %}} This page is a collection of resources and notes we've taken over the years.
{{% /notice%}}

## SCREEN

`screen` = creates new session

`screen -S name_of_session` (start a screen session with specific name)

`ctrl + A + D` = detaches screen

`screen -r` = reattaches if there's just one (i think)

`screen -r ####` (enough to be uniq) = reattaches specific screen 

`screen -list` or -ls (shows which screens are running

`screen -dr` (detach and reattach)

launch screen from remote server!!!! ie ssh into workstation (which won't log off) and then ssh into remote server (compute canada) from there
(a little more detailed info wouldnt hurt)