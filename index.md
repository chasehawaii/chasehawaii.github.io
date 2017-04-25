
# Table of contents

* [About ChaseHawaii](#about-chasehawaii)
* [Installation](#installation)
* [Goals](#goals)
* [Development history](#development-history)
  * [Milestone 1: Mockup Development](#milestone-1-mockup-development)
  * [Milestone 2: Data Model Development](#milestone-2-data-model-development)

# About ChaseHawaii
ChaseHawaii is a Meteor application designed specifically for the University of Hawaii community as a place to find relevant hikes, beach, restaurants and other adventures. The application is crowd sourced to provide ratings, comments, and easy to use filtering that finds adventures that are relevant and appealing to each user.

When you come to the site, you are greeted by the following landing page:

<img width="1452" alt="screen shot 2017-03-22 at 8 20 43 pm" src="https://cloud.githubusercontent.com/assets/21227204/25364955/89367daa-2901-11e7-8388-75e2d24ab8bb.png">

The landing page will link to the following login page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25364951/891644a4-2901-11e7-9523-281a3a17db97.png">

Once a user registers through the CAS authentication system, if they have a chase hawaii account they will be directed to the main item feeed. Otherwise they will be sent to the following create profile page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="
https://cloud.githubusercontent.com/assets/21227204/25365883/8728c148-2907-11e7-85ea-329907e082f2.png">

After a user has created a profile they will be able to see the items they have submitted and create a "bucket list" to save items they would like to do for later.

This page will change in that the user will have the number of reviews they've submitted which will be made unique for hikes/restaurants/beaches, if a user hits a certain number of reviews for any category, or hits another criteria. Their profile will display a "rank". For example if they review 50 restaurants they will have the rank "Explorer" displayed on their profile.

Here is the main item feed where users can filter through the different tags to find the adventure best suited for them: 
<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25364953/8917af1a-2901-11e7-9b97-8d2bd37aebc0.png">


Each user can submit their own adventure. The items will then be put up for approval from admins in order to avoid duplicate entries. Here is an example page for a beach adventure, displaying tags, location, the name of the beach, and a few comments.

Here are examples of each type of page.

Beach Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365462/924bfe12-2904-11e7-9a5f-7260662bb0cc.png">

Hike Page: 

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365782/d9175a9c-2906-11e7-86db-b8aaa656e9fd.png">


Restaurant Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365766/b97d5a2e-2906-11e7-960b-c547e332ee40.png">


The admin page will  have a place where the admin can approve, deny or contact the submitter for each submission.
<img width="1438" alt="screen shot 2017-03-22 at 8 23 01 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365782/d9175a9c-2906-11e7-86db-b8aaa656e9fd.png)
# Development history

## Milestone 1: Mockup development

This milestone started on April 6, 2017 and ended on April 12, 2017.

The goal of Milestone 1 was to create a mock-up of static HTML pages in the system. The mockup was developed as a Meteor app. In other words each page was a template that used FlowRouter to implement routing between pages. More pages to be added in the future as the need arises.

Mockups for the following four pages were implemented during M1:

<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25001077/6f95b896-1fdf-11e7-90fb-ff6d33b9a6cf.png">
<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/24983929/08067da4-1f86-11e7-9d43-1814c0b073b8.png">
<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/24983936/12713702-1f86-11e7-8479-a2580cc63829.png">
<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/24983937/146bfae2-1f86-11e7-943f-cf3bcd94b981.png">

Milestone 1 was implemented as [ChaseHawaii GitHub Milestone M1](https://github.com/chasehawaii/chasehawaii/projects/1)::

<img src="https://cloud.githubusercontent.com/assets/21227204/24984380/a72f269a-1f88-11e7-9287-d0137f40660c.png">


Milestone 1 consisted of thirteen issues, and progress was managed via the [ChaseHawaii GitHub Project M1](https://github.com/chasehawaii/chasehawaii/projects/1):

<img src="https://cloud.githubusercontent.com/assets/21227204/24984187/acd23ca0-1f87-11e7-8adc-f1f7a5e90a9f.png">

Each issue was implemented in its own branch, and merged into master when completed:

<img src = "https://cloud.githubusercontent.com/assets/21227204/24984427/0c33baba-1f89-11e7-8460-ae184e208c8b.png">

## Milestone 2: Data Model Development

This milestone started on April 11, 2017 and ended on April 27, 2017.
Current issues can be viewed via the [ChaseHawaii GitHub Project M2](https://github.com/chasehawaii/chasehawaii/projects/2)

The goal of Milestone 2 is to implement the data model: the underlying set of Mongo Collections and the operations upon them that would support the ChaseHawaii application. We are implementing the data model as a set of Javascript classes. The BaseCollection class provides common fields and operations. Then we have three classes (HikeCollection, BeachCollection, and the RestaurantCollection) classes that inherit from BaseCollection and provide the persistent data structures useful for ChaseHawaii. We are also implementing a UserCollection to support user accounts and user profiles.
