---
layout: post
title: "Auto assigned Jira Service Management based on Opsgenie on-call rotation"
date: 2024-01-10
published: true
tags:
  - development
  - jira
  - opsgenie
category: today
---

Previously, if someone create a Jira ticket on our Jira Service Management (service desk) ticketing system, it will auto-assigned to the person that i already assigned, and this person can quite overwhelmed with incoming ticket, event though we can route the ticket to another person, but the first impression will overwhelmed them. 

Because of that, i'm looking a way to automate the assignment of Jira Service Management based on Opsgenie on-call rotation, and it can be done easily.

First open your Jira Service Management, head to your service project, say the name is "IT Support Service Center", then you go to `Project Settings`, then you got to `Automation`.

Select `Create Rule`, name your rule, add your trigger, choose `Issue Created` then choose `Add Action`, choose `Assign Issue`, then choose `Assign to a user`, then choose `On-call responder` and choose the team that you want to have auto-assigned, then choose the on-call schedule name on that list.

Mine's look like this

![](/images/posts/jsm-opsgenie.png)

After this, you can create a new ticket, and it will auto-assigned to the on-call responder based on the schedule.