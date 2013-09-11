# Continuous Deployment
Lars Kluge, Hacker. 



Previously CTO and Cofounder of Kitchensurfing. 



## Definition



> Continuous Deployment is the **automated process of shipping** your product to production, with every push to master. 



## Motivation
- Earlier feedback for your business: get features in front of users as early as possible
- Faster development: develop, push, next feature
- Fewer merge conflicts
- Lower the risk of deployments
- Motivation for everyone involved: changes can be done immediately--no wait for the next scheduled release



## The Big Picture



![Overview](assets/images/big-picture.png)



## Who is using it?

Facebook, Etsy, Quora, Linkedin, …



## Is it practical for smaller startups?



# Yes.
We use it and love it at Kitchensurfing. 



## Our Stack
Ruby on Rails, MongoDB, Heroku, …



## Our Workflow



1. Pick up a ticket in Pivotal Tracker
2. Code
3. Commit with reference to ticket id
4. Pull Request on Github
5. Code Review
6. Multiple Staging Environments if manual check necessary
7. CI: Codeship runs test suite for pull request
8. Merge into master
9. Github notifies Pivotal Tracker that ticket is merged
10. CI runs again
11. On successful build, Codeship deploys to Heroku
12. Release Notes Email sent by Heroku



## Our Learnings



## MongoDB helps. 



# No Schema. 



## Etsy

![Etsy](assets/images/etsy-schema.png)

[source](http://www.slideshare.net/mikebrittain/mbrittain-continuous-deploymentalm3public)



## With MongoDB:

While (re)inventing your product, 

**no* schema migration** necessary. 



## Young product = a lot schema changes



## Trust your Test Suite



## Release Big Products in Small Pieces



## Use Feature Flags
Show new features only to your beta user group

Avoid the 'big bang' release



## Observe Production after Deploy
- Not only exception tracking
- How are business #s changing?
- Cloud behavior
- MMS Monitoring for MongoDB
- New Relic



## Behavior Change
- Is your team ready to make the behavior change?
- The whole team needs to support it. 
- Introduce Continuous Deployment as early as possible; it's getting harder down the road. 



## Product Team
How to break down features into small, easy to release pieces? What is the order of operation?



## Communication
- Keep your team in the loop
- Release Notes Email
- What is online, what's not?
- Ticket finished, does it mean it's online?



## Runtime of Test Suite
- &gt; 15 Min. tricky
- Context Switch is expensive for Engineers



## Heroku Preboot
``$ heroku labs:enable -a myapp preboot``



## Future Plans
- Better Release Notes Email based on finished stories in Tracker
- Statistics in Pull Request to understand the change based on compiled JS, CSS size, test suite build time, # of database queries, etc.
- Engineering Dashboard: See how a deploy changes business #s



## Thank you.

[larskluge.com](http://larskluge.com)

[@aekym](http://twitter.com/aekym)
