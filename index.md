
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

<img width="1452" alt="screen shot 2017-03-22 at 8 20 43 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880120/38c56792-34d1-11e7-8570-0870b5e2b696.png">

The landing page will link to the following login page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880241/f1b9f7c2-34d1-11e7-99a4-fd2ced850d4b.png">

Once a user registers through the CAS authentication system, if they have a chase hawaii account they will be directed to the main item feeed. Otherwise they will be sent to the following create profile page:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880304/537579b4-34d2-11e7-87d2-dd1735a89b05.png">

After a user has created a profile they will be taken to their profile page. Initially the page is mostly blank with the exception of what was added to their profile:

<img width="1446" alt="screen shot 2017-03-22 at 8 21 22 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880259/17521cee-34d2-11e7-9279-c1fb478ad9ce.png">

Once the user has created a profile they are free to browse through the items that have already been added and approved by other users. They can view the entire list by clicking the "Adventure Feed" Tab in the header. Once they click the tab they will be taken to the main item feed. The feed can be filtered to find specific items to best suit the type of adventure they are looking for: 

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880416/dea4f42e-34d2-11e7-877e-e45755c65deb.png">


Each user can also submit their own adventure. Here are the create pages. Each create page can be reached by clicking the "Create Adventure" Tab in the header. Once there the user is able to create an adventure by clicking on the appropriate tab. Here is the "Create Beach" Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880634/4e94d7da-34d4-11e7-8ce5-b49e9bc0cf8c.png">

The Create Hike Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880660/76d121cc-34d4-11e7-8298-084fe41c73c1.png">

And the Create Restaurant Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880660/76d121cc-34d4-11e7-8298-084fe41c73c1.png">


Once an item is created it will be sent to the following Admin Page for approval: 

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880060/d3b35508-34d0-11e7-8764-af74d232000d.png">

If the user finds an adventure they want to do, they can add it to their "bucket list" by clicking on the button. Once an item is on their bucket list it will be added to their profile page, where they can mark it as completed once they finish their adventure:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25880983/30625b14-34d6-11e7-984d-26e1e92c8ae7.png">


Beach Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365462/924bfe12-2904-11e7-9a5f-7260662bb0cc.png">

Hike Page: 

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365782/d9175a9c-2906-11e7-86db-b8aaa656e9fd.png">


Restaurant Page:

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25365766/b97d5a2e-2906-11e7-960b-c547e332ee40.png">

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

The goal of Milestone 2 was to implement the data model: the underlying set of Mongo Collections and the operations upon them that would support the ChaseHawaii application. We are implementing the data model as a set of Meteor Collections. Four seperate collections were created to handle each aspect of our web application. For the items there were three individual collections created, beaches, hikes, and restaurants. The collections were seperated as they have mostly different attributes. Each collection corresponds to different items on the items feed page. The profiles collection was created in order to manage the different profiles upon CAS login, each profile contains basic information about each user such as their username, first name, last name, social media info, etc.

Milestone 2 was implemented as [ChaseHawaii GitHub Milestone M2](https://github.com/chasehawaii/chasehawaii/milestone/2)::

<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25502196/67829c7a-2b31-11e7-8a35-e6a6da60289d.png">

Milestone 2 consisted of 20 issues and was managed via [ChaseHawaii GitHub Milestone M2](https://github.com/chasehawaii/chasehawaii/projects/2)

<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25503770/3303402a-2b37-11e7-8132-69023fa9f641.png">

Each issue was created into it's own branch then merged to master: 
<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25502195/677a9f84-2b31-11e7-8569-408e52a08912.png">

## Milestone 3: Authentication, Administration and Data Validation

This milestone started on April 27, 2017 and will end on May 9, 2017.
Current issues can be viewed via the [ChaseHawaii GitHub Project M3](https://github.com/chasehawaii/chasehawaii/projects/3)

During this Milestone, the team will implement error checks to validate data, ensure authentication throughout the application and fine tune functionality. 


