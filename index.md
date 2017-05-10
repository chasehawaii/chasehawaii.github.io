
# Table of contents

* [About ChaseHawaii](#about-chasehawaii)
* [Installation](#installation)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Development history](#development-history)
  * [Milestone 1: Mockup Development](#milestone-1-mockup-development)
  * [Milestone 2: Data Model Development](#milestone-2-data-model-development)
  * [Milestone 3: Milestone 3: Authentication, Administration and Data Validation](#milestone-3-authentication-administartion-and-data-validation)
* [Initial User Study](#initial-user-study)
  
# About ChaseHawaii
ChaseHawaii is a Meteor application designed specifically for the University of Hawaii community as a place to find relevant hikes, beach, restaurants and other adventures. The application is crowd sourced to provide ratings, comments, and easy to use filtering that finds adventures that are relevant and appealing to each user.

View the current working version of our web app here: <a href ="http://chasehawaii.meteorapp.com/item-feed">Chase Hawaii</a>

## User Guide

When you come to the site, you are greeted by the following landing page:


![landing_page](https://cloud.githubusercontent.com/assets/25087813/25884633/6d1e41e4-34ef-11e7-9a29-4883620f65ca.png)

The landing page will link to the following login page:



![log_in](https://cloud.githubusercontent.com/assets/25087813/25884711/0f71dff0-34f0-11e7-8ce3-29aa52b83db0.png)

Once a user registers through the CAS authentication system, if they have a ChaseHawaii account they will be directed to the main item feed. Otherwise they will be sent to the following create profile page:


![create_profile](https://cloud.githubusercontent.com/assets/25087813/25884714/10bd34c2-34f0-11e7-864d-3232ea6d5c53.png)


After a user has created a profile they will be taken to their profile page. Initially the page is mostly blank with the exception of what was added to their profile:

![profile](https://cloud.githubusercontent.com/assets/25087813/25884716/12648eec-34f0-11e7-87a4-da7bb3f49016.png)


Once the user has created a profile they are free to browse through the items that have already been added and approved by other users. They can view the entire list by clicking the "Adventure Feed" Tab in the header. Once they click the tab they will be taken to the main item feed. The feed can be filtered to find specific items to best suit the type of adventure they are looking for: 

![adventure_feed](https://cloud.githubusercontent.com/assets/25087813/25884719/13ba0916-34f0-11e7-898d-9fe570b5f19a.png)

Each user can also submit their own adventure. Here are the create pages. Each create page can be reached by clicking the "Create Adventure" Tab in the header. Once there the user is able to create an adventure by clicking on the appropriate tab. Here is the "Create Beach" Page:



![beach](https://cloud.githubusercontent.com/assets/25087813/25884980/a2c4cb72-34f1-11e7-877f-f891567f4384.png)


The Create Hike Page:

![hike](https://cloud.githubusercontent.com/assets/25087813/25884983/a3e9dab0-34f1-11e7-9061-e9c675f50df0.png)

And the Create Restaurant Page:

![restaurant](https://cloud.githubusercontent.com/assets/25087813/25884984/a5166368-34f1-11e7-8451-137ddb258f9e.png)


Once an item is created it will be sent to the following Admin Page for approval: 

![admin](https://cloud.githubusercontent.com/assets/25087813/25884988/a6918466-34f1-11e7-8feb-c806f8d605b7.png)


Since the application's content is crowdsourced, it was imperative to include administrative abilities to ensure that all the content featured is appropriate, not offensive, and not a duplicate entry of an already existing item. Users also have the right to request that the items they make be deleted, which will then show up on the admin's page, where the admin can make the final step in deleting the item. Currently, the only accounts with administrative abilites are those who have developed the application.

If the user finds an adventure they want to do, they can add it to their "bucket list" by clicking on the button. Once an item is on their bucket list it will be added to their profile page, where they can mark it as completed once they finish their adventure:

![profile2](https://cloud.githubusercontent.com/assets/25087813/25884992/a80b73a6-34f1-11e7-819e-1869c7b225f0.png)


Each item can be expanded for a more detailed view, user can leave comments and click on other user's profiles to view other users profile pages.

Here is an example of a the detailed Beach Page:

![sandys](https://cloud.githubusercontent.com/assets/25087813/25884993/a98b990e-34f1-11e7-9e69-9b2213d71986.png)


Hike Page: 

![hike_item](https://cloud.githubusercontent.com/assets/25087813/25884996/ace7c136-34f1-11e7-8cda-3c0b0b108c39.png)

Restaurant Page:

![restaurant_item](https://cloud.githubusercontent.com/assets/25087813/25884998/ae5b776a-34f1-11e7-9ae7-8b1850411fa3.png)


And the Public Profile page:

![public_profile](https://cloud.githubusercontent.com/assets/25087813/25885000/b07fadae-34f1-11e7-8b2f-c6522cd922c1.png)

Several other pages were added to the site that can be accessed through the footer. If users want to know more about the site and they can view it on the About page:

![about](https://cloud.githubusercontent.com/assets/25087813/25885001/b1e3766c-34f1-11e7-861a-e95025f7d058.png)


If a user wants to contact any of the admins they can find the necessary info through the contact us link in the footer, here is a view of the contact page: 

![admin_contact](https://cloud.githubusercontent.com/assets/25087813/25885003/b3631f24-34f1-11e7-892e-abd0e7c7af5b.png)


## Developer Guide

First, install Meteor.

Second, download a copy of ChaseHawaii, or clone it using git.

Third, cd into the app/ directory and install libraries with:

```
$ meteor npm install
```

Next, enable the CAS System, put CAS settings in Meteor.settings (for exemple using METEOR_SETTINGS env or --settings) like so:

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

## Milestone 3: Authentication Administration and Data Validation

This milestone started on April 27, 2017 and ended on May 9th, 2017.
Current issues can be viewed via the [ChaseHawaii GitHub Project M3](https://github.com/chasehawaii/chasehawaii/projects/3)

The goal of milestone 3 was to improve the functionality of our webpage, create an admin page to ensure a better user experience, create a working login system with the CAS system, and to validate the data within our collections. From milestone two significant functional improvements were made. 

For the profile pages users are now able to update their pictures, which will be displayed when they comment on different items. By clicking on another users profile picture they will be redirected to that users public profile page. The functionality of the like and bucket list functions were improved so that items would correctly be added to a users profile page. Users can also display what items they have completed, and which items they have liked.

The Administrator's page has also been implemented to help moderate the content that users post. The admin has three abilities: approval of an item, denial of an item, and the deletion of an item. In order to keep content in check, when a user creates an item, it is placed in a "pending" state, in which it will not be displayed to other users. Only an admin can view the item's info on the admin page. At that point, he/she can decide if it is ready to display by "approving" it, or "deny" it to indicate to the user that it is an unsatisfactory item. A user has the right to request the deletion of an item, which the admin can see on their page and follow through with the act of deletion. 

Milestone 3 was implemented as [ChaseHawaii GitHub Project M3](https://github.com/chasehawaii/chasehawaii/milestone/3)::


<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25883309/42b47d1a-34e5-11e7-9f6f-459ab24fb0c9.png">


Milestone 2 consisted of 20 issues and was managed via [ChaseHawaii GitHub Milestone M2](https://github.com/chasehawaii/chasehawaii/projects/3)

<img width="1423" alt="screen shot 2017-03-22 at 8 22 06 pm" src="https://cloud.githubusercontent.com/assets/21227204/25883306/406e1796-34e5-11e7-84e9-13cd0c7ff75e.png">


Each issue was created into it's own branch then merged to master: 


<img width="1437px" src="https://cloud.githubusercontent.com/assets/21227204/25883304/3de6bbf4-34e5-11e7-8172-2145ed450405.png">


## Initial User Study

To test our web application five members of the UH community were recruited from various majors and class standings. The feedback was collected via email after the users had tested our website. 

Nathan Nahina, Junior, Computer Science:

Nice landing page I like the layout and simplicity, maybe after logging in, can have something pop up or change on the landing page to direct you where to go next, Honolulu tag spelled wrong, could not add beach, filter search was cool, like the aesthetics, just need more functionality

Michael Serai, Junior, Computer Science:

Asthetically the main page is very pleasing, not overbearing. When we add items to the list, maybe add a gps feature for directions. Not sure if you are able to site other sources. This way, we wouldn't have to add our own pictures for restaurants. Otherwise I like the add feature. The adventure feed is nice, maybe categorize them in columns for easier viewing. Otherwise really solid, I like.

Aviv Suan, Graduate Student, Natural Resource and Environmental Management:

Cool website and great idea.  I really like the layout and captivating pictures.  The login and logout button could be highlighted when hovering over the button to indicate an interactive button.  

Kalani Sanidad, Junior, Computer Science:

CONS:
The first thing i noticed was that it didn't scale to mobile, but it should be fine. When i open it up on browser, i tried scaling it every which way. when i did, the "getting started" didn't move with the scaled page. for that, that is a minor fix. When you submit, there was no indication of success or failed. Login didn't work(yes i have a dev environment login)
Add comment doesn't work, I am guessing nothing works when you aren't logged in. On the adventure feed maybe add search text box for searching a specific place. On the create adventure page maybe start off with a default form. and have the buttons highlighted.

PRO:
For one, it made it easy for me to find the login and logout. There isn't much there so for users that don't know much about technology(and i know a couple of surfers would like something like this) and have it easy for them. There is a checklist for tourist to do adventurous stuff since that is something newly weds would like to do.... or i would think so. Idon't know what is supposed to be on the profile page, but i am guessing that it looks well. If everything works, it would give it 4.8/5,  but for now 3/5 because login couldn't work and once that works, it should go up.  

Ted Jacoby, Senior, Biochemistry:

Sick site. I like the images. Really crisp. Very simple and user-friendly 

Seems like it's tourist oriented. Maybe have another section on hotels/BB/vacation rentals? Just a suggestion for the sake of being critical. It's good.






