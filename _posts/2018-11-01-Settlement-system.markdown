---
title: "Settlement System"
layout: post
date: 2018-11-01
tag: 
    - Merchant Settlement
    - Pricing Engine
    - Credit Card
    - Project Integration
headerImage: false
projects: true
hidden: false # don't count this post in blog pagination
description: "This was one of the longest running projects that I did. It had the toughest business logic I have ever seen untill writing this post."
category: project
author: pranjal
externalLink: false
---

## Summary:
This was one of the longest running projects that I had worked on. It had the toughest and most complicated business logic I had ever come across. Having said that, keeping the code simple, straightforward and easy to understand inspite of that amount of complexiety was a challenge in itself. Throughly enjoyed working on this one.

---

### Tech stack:
* Struts
* JSP
* MySQL
* JDBC

---

### Further reading:
Unlike others, this was not a project that was started from scratch. This was one of the projects that was being used by operators on a regular basis. However, this time it had major changes to be incorporated. These changes would reshape the entire project.

This project was integrated with [Loan Collection System][1] to provide a wholesome view of the entire ecosystem. This project basically focused on merchant payouts. For any instrument the merchant used, this project was capable of processing merchant payouts in minimum possible amount of time. 

*Merchant Settlement and Payout* is a complex topic. In addition to account for all the money that flows through the system and handle *refund* and *chargeback*, this project gave operators the ability to hold merchant payouts in lieu of suspicious transactions.

>The aim of the project was to achieve *same day settlement*, in turn making the merchant happier.

A *Pricing Engine* was developed, which took care of calculations for every possible permutation of merchant account, payment instrument (credit/debit card used for making payment), product subscribed and any pending fee, charges, refund or chargeback that the merchant might have.

[1]: {{site.url}}/Loan-Collection-System