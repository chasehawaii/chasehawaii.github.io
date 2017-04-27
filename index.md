
# Table of contents

* [About ChaseHawaii](#about-chasehawaii)
* [Installation](#installation)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Goals](#goals)
* [Development history](#development-history)
  * [Milestone 1: Mockup Development](#milestone-1-mockup-development)
  * [Milestone 2: Data Model Development](#milestone-2-data-model-development)

# About ChaseHawaii
ChaseHawaii is a Meteor application designed specifically for the University of Hawaii community as a place to find relevant hikes, beach, restaurants and other adventures. The application is crowd sourced to provide ratings, comments, and easy to use filtering that finds adventures that are relevant and appealing to each user.

View the current working version of our web app here: <a href ="http://chasehawaii.meteorapp.com/item-feed">Chase Hawaii</a>

## User Guide

When you come to the site, you are greeted by the following landing page:

<img width="1452" alt="screen shot 2017-03-22 at 8 20 43 pm" src="https://cloud.githubusercontent.com/assets/21227204/25364955/89367daa-2901-11e7-8388-75e2d24ab8bb.png">

The landing page will link to the following login page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25364951/891644a4-2901-11e7-9523-281a3a17db97.png">

Once a user registers through the CAS authentication system, if they have a chase hawaii account they will be directed to the main item feeed. Otherwise they will be sent to the following create profile page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365883/8728c148-2907-11e7-85ea-329907e082f2.png">

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

## Developer Guide

First, install Meteor.

Second, download a copy of ChaseHawaii, or clone it using git.

Third, cd into the app/ directory and install libraries with:

```
$ meteor npm install
```

Third, enable the CAS System, put CAS settings in Meteor.settings (for exemple using METEOR_SETTINGS env or --settings) like so:

```
"cas": {
    "baseUrl": "https://sso.univ-pau.fr/cas/",
    "autoClose": true
},
"public": {
    "cas": {
        "loginUrl": "https://sso.univ-pau.fr/cas/login",
        "serviceParam": "service",
        "popupWidth": 810,
        "popupHeight": 610
    }
}

```

Then, to start authentication, you have to call the following method from the client (for example in a click handler) :

```
Meteor.loginWithCas([callback]);
It must open a popup containing you CAS login from. The popup will be close immediately if you are already logged with your CAS server.
```
Next, the system uses the moment.js package for the date and time throughout the application. Run the following to install the package:

```
$ meteor add mrt:moment
```

Finally, run the system with:

```
$ meteor npm run start
```

The application will appear at [http://localhost:3000](http://localhost:3000). If you have an account on the UH test CAS server, you can login. From the login follow the <a href = "#user-guide">user guide</a> for a detailed summary on the flow of the web app.

## Milestone 2: Data Model Development

This milestone started on April 11, 2017 and ended on April 27, 2017.
Current issues can be viewed via the [ChaseHawaii GitHub Project M2](https://github.com/chasehawaii/chasehawaii/projects/2)

The goal of Milestone 2 was to implement the data model: the underlying set of Mongo Collections and the operations upon them that would support the ChaseHawaii application. We are implementing the data model as a set of Meteor Collections. Four seperate collections were created to handle each aspect of our web application. For the items there were three individual collections created, beaches, hikes, and restaurants. The collections were seperated as they have mostly different attributes. Each collection corresponds to different items on the items feed page. The profiles collection was created in order to manage the different profiles upon CAS login, each profile contains basic information about each user such as their username, first name, last name, social media info, etc.

Milestone 2 was implemented as [ChaseHawaii GitHub Milestone M2](https://github.com/chasehawaii/chasehawaii/milestone/2)::

<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25502196/67829c7a-2b31-11e7-8a35-e6a6da60289d.png">

Milestone 2 consisted of 20 issues and was managed via [ChaseHawaii GitHub Milestone M2](https://github.com/chasehawaii/chasehawaii/projects/2)

<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25503770/3303402a-2b37-11e7-8132-69023fa9f641.png">

Each issue was created into it's own branch then merged to master: 
<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25502195/677a9f84-2b31-11e7-8569-408e52a08912.png">


