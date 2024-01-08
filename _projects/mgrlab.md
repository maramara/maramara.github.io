---
layout: project-page
title: Memgraph Lab
description: Designing a solution for querying data
thumbnail: /assets/img/mgrlab/img-mgrlab.jpg
image: /assets/img/mgrlab/head-mgrlab.png
order: 4
---

| Client:		| Memgraph Ltd |
| Deliverables:	| Desktop & web application (v1.0) |
| Time:		    | June 2018 - Nov 2018 |
| Team:		    | Product &amp; Business dev, 2 full-stack engineers |
| My role:		| UX/UI Designer|

## Introduction 

Memgraph is the world's first real-time distributed graph database, which aims to deliver high-performance at enterprise scale. 
It is engineered to support the needs of enterprises with colossal amounts of data. Memgraph aims to help businesses harness the power of real-time connected data, so they can build the next generation of intelligent applications.


## Problem space

The product was expanding beyond purely CLI use and needed to create an application that provides a graphical user interface to manipulate graph database data.

## Research

Research continued based on the initial one made for the [same company](/projects/mgr/), this time focusing more at gathering feedback from users (through surveys) that primarily manipulate database data.

### Problems defined

- How to enable data scientists to get insights from the data?
- How to visualise complex graph database query results?
- What is needed to monitor and maintain the database?
- How to make running queries easier?

### Goals

- Ensure obtaining a better market share by making the database product more usable

### Target audience

- System administrator
- Database administrator
- Data analyst &amp; Developer

## Ideation and validation

In the first (beta) iteration of the project, we tried to focus on two activities for the users: monitoring and querying data at the same time.
Another point of focus was exploration of the querying process where users should be enabled to perform consecutive database queries, save them and also search for them.

![Memgraph Lab Wireframes](/assets/img/mgrlab/mgrlab-wf.jpg)
*Memgraph Lab Wireframes*

### Key findings

I tested our assumptions by setting up unmoderated usability studies based on the lo-fi prototypes that were created out of Sketch wireframes.
Key findings that were discovered during the research:

- Different user roles want to use tools tailored to their needs
- Users need a seamless way to interconnect tools that they are using (management vs. querying)
- The space to run and manage queries needs to be distraction-free zone

Monitoring and querying of data proved to not work well for users because they wanted to focus on one action at the time, depending on their role (for example, a business analyst might not be interested to know what is the workload of the database).
The overview of database queries with separate lists for query history and favorites proved to work better for users.

## UI design 

UI design of the application follows the [previously established](/projects/mgr/) look and feel of the brand.
In two iterations, there were adjustments to the statistics on the dashboard (based on user feedback) and top navigation was removed since this is a desktop application. 
Project frontend was developed by reusing existing components and styles.

![Memgraph Lab UI](/assets/img/mgrlab/mgrlab-ui.jpg)
*Memgraph Lab UI*

## Project outcomes

The beta version of the project was published on time and is freely available at [memgraph.com](https://memgraph.com). 