---
title: "Project Mu"
layout: post
date: 2017-11-03
tag: 
    - Spring Boot
    - Java Reflection
    - Google Guava
    - MQTT
    - Trust Establishment
    - Mosquitto Message Broker
image: https://mosquitto.org/images/mosquitto-text-side-28.png
headerImage: true
projects: true
hidden: false # don't count this post in blog pagination
description: "This was a integration based project wherein we used different kinds of technologies for different kinds of tasks."
category: project
author: pranjal
externalLink: false
---

## Summary:
This was one of the most ambitious projects that I had worked on. It included vast amount of technologies.

---

### Tech stack:
<div class="side-by-side">
    <div class="toleft">
        <ul>
            <li>JWT</li>
            <li>Spring Boot</li>
            <li>Maven</li>
            <li>Spring Security</li>
            <li>Spring AOP</li>
            <li>Java Reflection</li>
            <li>Google Guava</li>
        </ul>
    </div>
    <div class="toright">
        <ul>
            <li>MQTT</li>
            <li>OAuth2</li>
            <li>Hibernate</li>
            <li>MySQL</li>
            <li>OkHttp3</li>
            <li>Eclispe Paho</li>
            <li>Mosquitto Message Broker</li>
            <li>AWS EC2, RDS, SNS</li>
        </ul>
    </div>
</div>

---

### Further reading:
**Spring Boot** was the choice of framework because of its ease of use, a huge community support and excellent documentation. **Maven** was used as a build tool. The resulting *jar* after *Maven* build was deployed on **AWS EC2** instance which was maintained in the same *security group* as an **AWS RDS** instance. Having *EC2* and *RDS* in the same security group increased security to the database. **AWS SNS** was also used to send *OTP*s to mobile devices across globe.

One *authorization server* and multiple *resource servers* were deployed on various *AWS EC2* instances. Clients had to connect to the service via a **Jason Web Token, JWT**. *JWTs* were generated by the authorization server and could be used on any of the resource servers. However, the authorization and resource servers need to trust each other before a *JWT* generated on the authorization server can be accepted at the resource server. This **trust establishment** was done before the services boot up.

In addition to protect notifications from being exposed to outer world, we decided to implement our own Push Notification System. In an efforrt to do this, we implemented the **MQTT Protocol** using *Eclipse Paho* libaray. *Eclispe Paho* is like the client to **Mosquitto Message Broker**  which is a simple message broker similar to *Rabbit MQ*. The Push Notification system worked on a *Pub-Sub* model where clients were subscribed to specific channel where notifications were published.

*MQTT* is one of the vastly used protocols in *IOT*. Since IOT devices generally work at a location where internet connection can not be guranteed, *MQTT* has a much lesser footprint as compared to *HTTP*. The messages exchanged in *MQTT* are strings of *0*s and *1*s. It is the responsibility of the client to make sense of the messages and then display them in the notification tray of the device. Also, the client needs to take care while development, because incorrect development may lead to reduced battery performance on the device.

For one of the use case, name of some java classes were stored in the database and **Java Reflection** was used to call methods of that calss. These classes represented different flows the client could take in its lifecycle within the system. The database used was a **MySQL** database with **Hibernate** used as an *ORM*. This database was deployed on **AWS RDS**. Also, the databse maintained audit trail of each and every operation performed by the service. This was achieved using **Spring AOP**.

Stay tuned for a blog post about **Basics of Spring AOP**.