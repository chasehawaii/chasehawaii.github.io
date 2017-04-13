
# Table of contents

* [About ChaseHawaii](#about-chasehawaii)
* [Installation](#installation)
* [Goals](#goals)
* [Development history](#development-history)
  * [Milestone 1: Mockup development](#milestone-1-mockup-development)

# About ChaseHawaii
ChaseHawaii is a Meteor application designed specifically for the University of Hawaii community as a place to find relevant hikes, beach, restaurants and other adventures. The application is crowd sourced to provide ratings, comments, and easy to use filtering that finds adventures that are relevant and appealing to each user.

When you come to the site, you are greeted by the following landing page:

The landing page will link to the login page, the contact us page, and the about us feed. 

In the future we will add event handlers to each of the buttons. So that users can easily see where they will be redirected to.
<img width="1452" alt="screen shot 2017-03-22 at 8 20 43 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234642/8e65c73c-0f3d-11e7-96b5-513a6d53bcd1.png">

After a user is logged in they will be directed to their home page. This is the user's profile page where they can see the items they have submitted and create a "bucket list" to save items they would like to do for later.

This page will change in that the user will have the number of reviews they've submitted which will be made unique for hikes/restaurants/beaches, if a user hits a certain number of reviews for any category, or hits another criteria. Their profile will display a "rank". For example if they review 50 restaurants they will have the rank "Explorer" displayed on their profile.


<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234663/a748707e-0f3d-11e7-843a-0db327e6b148.png">

This is a create profile page for new users.

The page will have an "Age" and "Class Standing" Drop down selections.

<img width="1445" alt="screen shot 2017-03-22 at 8 22 52 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234691/bd11a84e-0f3d-11e7-91a1-e04584f39cee.png">

Here is the main adventure item feed.

It will eventually have filter functionality to filter by category(difficulty, type of food, etc.), tags or number of likes.

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234652/981b2f6a-0f3d-11e7-9393-97fa85a04e13.png">


Each user can submit their own adventure. This one is for a hike, but an initial dropdown will decide what form the user gets to fill out. Some of the fields will be used to auto-create tags that can be filtered on in the main adventure feed page. 

Items created on this page will be reviewed by an admin before being added to avoid duplicate items and false information.

<img width="1437" alt="screen shot 2017-03-22 at 8 21 35 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234656/9e1761f4-0f3d-11e7-8aa5-be82dd65511e.png">

This is a page for a specific adventure item. This will provide full details and a place where users can comment

The page will feature a rating system. Users comments can be "up/downvoted". 

<img width="1432" alt="screen shot 2017-03-22 at 8 22 22 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234670/af46b6fa-0f3d-11e7-8b7a-8a3c2f8b7eb7.png">
<img width="1197" alt="screen shot 2017-03-22 at 8 22 34 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234682/b666eb08-0f3d-11e7-92c6-467ee6fb2d7c.png">

About page
<img width="1439" alt="screen shot 2017-03-22 at 8 22 43 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234688/ba926fe0-0f3d-11e7-810b-8e50e73e537d.png">

Th admin page will  have a place where the admin can approve, deny or contact the submitter for each submission.
<img width="1438" alt="screen shot 2017-03-22 at 8 23 01 pm" src="https://cloud.githubusercontent.com/assets/25087813/24234695/c05a7b34-0f3d-11e7-892e-dca37bc6dc27.png">

# Development history

## Milestone 1: Mockup development

This milestone started on April 6, 2017 and ended on April 12, 2017.

The goal of Milestone 1 was to create a mock-up of static HTML pages in the system. The mockup was developed as a Meteor app. In other words each page was a template that used FlowRouter to implement routing between pages. More pages to be added in the future as the need arises.

Mockups for the following four pages were implemented during M1:

<img width="200px" src="https://cloud.githubusercontent.com/assets/21227204/25001077/6f95b896-1fdf-11e7-90fb-ff6d33b9a6cf.png">
<img width="200px" src="https://cloud.githubusercontent.com/assets/21227204/24983929/08067da4-1f86-11e7-9d43-1814c0b073b8.png">
<img width="200px" src="https://cloud.githubusercontent.com/assets/21227204/24983936/12713702-1f86-11e7-8479-a2580cc63829.png">
<img width="200px" src="https://cloud.githubusercontent.com/assets/21227204/24983937/146bfae2-1f86-11e7-943f-cf3bcd94b981.png">

Milestone 1 was implemented as [ChaseHawaii GitHub Milestone M1](https://github.com/chasehawaii/chasehawaii/projects/1)::

<img src="https://cloud.githubusercontent.com/assets/21227204/24984380/a72f269a-1f88-11e7-9287-d0137f40660c.png">


Milestone 1 consisted of thirteen issues, and progress was managed via the [ChaseHawaii GitHub Project M1](https://github.com/chasehawaii/chasehawaii/projects/1):

<img src="https://cloud.githubusercontent.com/assets/21227204/24984187/acd23ca0-1f87-11e7-8adc-f1f7a5e90a9f.png">

Each issue was implemented in its own branch, and merged into master when completed:

<img src = "https://cloud.githubusercontent.com/assets/21227204/24984427/0c33baba-1f89-11e7-8460-ae184e208c8b.png">

## Milestone 2: Data Model Development

This milestone started on April 11, 2017 and is expected to end on April 25, 2017.
Current issues can be viewed via the [ChaseHawaii GitHub Project M2](https://github.com/chasehawaii/chasehawaii/projects/2)

The goal of Milestone 2 is to implement the data model: the underlying set of Mongo Collections and the operations upon them that would support the ChaseHawaii application. We are implementing the data model as a set of Javascript classes. The BaseCollection class provides common fields and operations. Then we have three classes (HikeCollection, BeachCollection, and the RestaurantCollection) classes that inherit from BaseCollection and provide the persistent data structures useful for ChaseHawaii. We are also implementing a UserCollection to support user accounts and user profiles.
