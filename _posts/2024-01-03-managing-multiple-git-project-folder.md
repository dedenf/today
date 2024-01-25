---
layout: post
title: "Manage Multiple git project folder"
date: 2024-01-03
published: true
tags:
  - development
  - git
  - codes
category: today
---

Managing multiple git project can be cumbersome, even just for updating the code, like pulling the latest code from the remote repository.

For instance i have these project

```
➜ ls -1
bla-android
bla-platform
blalslda
open-bla
billblabal
edithing
bla-blog
bla-handler
bla-fin
wednes
in-app
saturca
some-manifest
code-backup
doing-internal
is-there-news
protect-plus
protect-plus-the-second
notsomething
onboarding
blanking-the-new
curious
someform
verosomeform
vision-plus
angle-plus
some-text-collection
```
If we wanted to update the code for all of these project, we have to do it manually, `cd` to the folders then so some `git pull` for each folder, we can use shell command like `find . -name .git -print -execdir git pull \;`, the command will find the git project folder and then execute each folder's git pull command, to make things easier, we can make an alias for the command like `alias git-pull-all='find . -name .git -print -execdir git pull \;'`, now we can just type `git-pull-all` and it will execute the command for all the git project folder.

Or, you could use a python package, called [`gita`](https://github.com/nosarthur/gita), it will help you to manage multiple git project folder, and it feels flexible because we can relay the git command to the package, so we can do something like `git pull` or `git push` to update all the git project folder.

Adding git project to gita

```bash
$ gita add <folder-name>
```

or you want to add all or the folder in one particular folder

```bash
$ gita add -a <folder-name>
```

Get latest information from each folder

```bash
➜ gita ll
repo1   development []     [FN-9961] FDS extra onboarding (2 hours ago)
repo2   develop    []      Merge branch 'enhance/unit-test-coverage' into 'develop' (3 weeks ago)
repo3   main       []      Merge branch 'feature' into 'main' (2 years, 9 months ago)
repo4   main       []      add service partner (2 years, 1 month ago)
repo5   main       []      Merge branch 'releases/rb-v1.35.0' into 'main' (3 weeks ago)
repo6   main       []      Merge branch 'ADO-1739-base-image-jupyterhub' into 'main' (3 months ago)
repo7   main       []      second init(?) (9 months ago)
repo8   develop    []      Merge branch 'staging' into develop (4 months ago)
repo9   main       []      Merge tag 'release-v1.33.0' (5 weeks ago)
repo10  main       []      Add MP pubsub subscription IAM grant (4 weeks ago)
repo11  development []     [FUN-5663]  Webview (3 weeks ago)
repo12  develop    []      Update BDS CI/CD Production (2 weeks ago)
repo13  main       [$]     Update platformbanking image to 9587cd35 (43 minutes ago)
repo14  main       []      progressing optimization 10% (5 months ago)
repo15  staging    []      remove unused api (4 months ago)
repo16  master     []      add new fopml feed from reeder (1 year, 3 months ago)
repo17  main       [$]     [int][dev]update mobile api dev (6 hours ago)
repo18  main       []      add file for DRC (4 months ago)
repo19  develop    []      Merge branch 'BM-32353-dev' into 'develop' (34 hours ago)
repo20  develop    []      Merge branch 'bypass_dev' into 'develop' (3 weeks ago)
repo21  develop    []      Merge branch 'ms_UTP-7013' into 'develop' (54 minutes ago)
repo22  main       []      Merge branch 'rc_v.2.4.0_into_main' into 'main' (3 weeks ago)
repo23  main       []      remove fluentd (4 weeks ago)
repo24  main       []      update roles datadog & telegraf (8 weeks ago)
repo25  main       []      change readme (5 months ago)
repo26  main       []      add more text for test (1 year, 3 months ago)
```

We can have a fresh pulled repo using one command, or do some git command within one command, like `gita pull` or `gita push`

But of course, we could still using the old way by using good old `find`.

```bash
find . -name .git -print -execdir git pull --rebase \;
```

Or you could always add it to your `.bashrc` or `.zshrc`

```bash
alias gitupdate='find . -name .git -print -execdir git pull --rebase \;'
```
