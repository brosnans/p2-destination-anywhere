# Milestone Project - Destination Anywhere

*Developer: sarahloh*

- [Project Brief](#project-brief)
- [Technologies](#technologies-and-dependencies)
- [UXD](#uxd)
- [Wireframes](#wireframes-and-mockups)
- [Deployment](#deployed-to-github-pages)
- [Tests and Fixes](#tests-and-fixes)

### Project Brief

**Create a Single Page Application that relies heavily on one or more APIs**

In this project, you’ll be building a frontend-only website using the technologies that you have learned throughout Interactive Frontend Development.

- Create a site that calls on the Google Maps API and/or the Google Places API (or similar) to allow users to search for their next holiday destination.

You'll want help your users:

- Select a destination city
- Find tourist attractions
- Find accommodation
- Find bars and restaurants
- Provide search results in a manner that is visually appealing for your user (by drawing on the skills you have learned in User-Centric Frontend Development)


### Technologies and Dependencies

- [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
- [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3)
- [Bootstrap v4.1.0](https://getbootstrap.com/docs/4.1/)
- - https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css
- - https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js
- [Font Awesome v4.7.0](https://fontawesome.com/v4.7.0/)
- - https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css
- [jQuery v3.3.1](https://jquery.com)
- - https://code.jquery.com/jquery-3.3.1.min.js
https://developers.google.com/maps/documentation/javascript/tutorial- [Google Maps API](https://developers.google.com/maps/documentation/javascript/tutorial)
- [Animate.css](https://daneden.github.io/animate.css/)


### UXD

#### Strategy

| Focus                               | User Needs                                          | Business Objectives                           |
|-------------------------------------|-----------------------------------------------------|-----------------------------------------------|
| What are you aiming to achieve?     | Select a destination city                           | Increase brand awareness                      |
|                                     | Find tourist attractions                            | Increase social media following               |
| For whom?                           | Find accommodation                                  |  |
| TARGET AUDIENCE - Adults            | Find bars and restaurants                           |  |
|                                     |  |  |

#### Scope

| Focus                               | Functional Specification                                    | Content Requirements                                                      |
|-------------------------------------|-------------------------------------------------------------|---------------------------------------------------------------------------|
| Which features?                     | Explore - View cities list by country                       | View cities by country                                                    |
|                                     | Navigate - Use the map to discover cities                   | Select city from dropdown                                                 |
| What’s on the table?                | Discover - Browse attractions, accommodation and restaurants| Type city name into search box                                            |
|                                     | ~~Weather - View current weather data~~                     | Navigate to and select city using map                                     |
|                                     |                                                             | Toggle tourist attractions, accommodation, bars and reataurants markers   |
|                                     |                                                             | Display image and information for each venue                              |
|                                     |                                                             | Display images and information for city                                   |
|                                     |                                                             | ~~Display weather charts~~                                                    |

#### Structure

| Focus                               | Interaction Design                                                           | Information Architecture                                                               |
|-------------------------------------|------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| How is the information structured?  | Where am I? / How did I get here? / What can I do here? / Where can I go?    | Organizational / Navigational schemas (tree / nested list / hub and spoke / dashboard) |
|                                     |                                                                              |                                                                                        |
|                                     | Explore > Navigate > Discover > Venue                                        | Tree                                                                                   |
| How is it logically grouped?        | Mobile: Buttons and chevron arrows move between various sections             |  |
|                                     | Tablet and Desktop: Click to sections                                       |  |
|                                     |  |  |

#### Skeleton

| Focus                                                       | Interface Design      | Navigational Design                             | Information Design  |
|-------------------------------------------------------------|-----------------------|-------------------------------------------------|---------------------|
| How will the information be represented?                    | See wireframes        | Explore > Navigate > Discover > Venue           |                     |
|                                                             |  |  |  |
| How will the user navigate to the information and features? |  |  |  |
|                                                             |  |  |  |
|                                                             |  |  |  |
|                                                             |  |  |  |
|                                                             |  |  |  |

#### Surface

| Focus                                                       | Visual Design                       |
|-------------------------------------------------------------|-------------------------------------|
| What will the finished product look like?                   |  |
|                                                             |  |
| What colours, typography and design elements will be used?  | @import url('https://fonts.googleapis.com/css?family=Montserrat:300,600&#124;Open+Sans'); |
|                                                             |  |
|                                                             |  |

#### Wireframes and Mockups

![Wireframe 1](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/wireframe-1.JPG)

![Wireframe 2](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/wireframe-2.JPG)

![Wireframe 3](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/wireframe-3.JPG)

*Mobile*

![Mockup - Mobile](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/mockup-mobile.jpg)

*Tablet*

![Mockup - Tablet](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/mockup-tablet.jpg)

*Desktop*

![Mockup - Desktop](https://raw.githubusercontent.com/sarahloh/p2-destination-anywhere/master/assets/wireframes/mockup-desktop.jpg)

### Deployed to Github Pages

- Go to project repo settings on Github
- Select master branch and click save
- Project link: [https://sarahloh.github.io/p2-destination-anywhere/](https://sarahloh.github.io/p2-destination-anywhere/)

### Tests and Fixes

[**HTML Validator Results**](https://validator.w3.org/nu/?doc=https%3A%2F%2Fsarahloh.github.io%2Fp2-destination-anywhere%2F)

[**CSS Validator Results**](https://jigsaw.w3.org/css-validator/validator?uri=https%3A%2F%2Fsarahloh.github.io%2Fp2-destination-anywhere%2F&profile=css3svg&usermedium=all&warning=1&vextwarning=&lang=en)


#### *Mobile*

Tested on iPhone 5
---

**PROBLEM**

Legend not reset on change city

**FIX**

```javascript
// Reset legend
$('.legend-btn').children('i').removeClass("invisible");
```

---

**PROBLEM**

Contents overflowing header on phone screen

**FIX**

Adjust height of header and navbar

---

**PROBLEM**

Back icon not returning to home from navigate

**FIX**

setCuttentSection was incorrect

```javascript
// home button clicked
$('.home a').click(function () {
    if (xs || sm) {
        if ($(this).attr('href').substr(1) == "explore") {
            toggleElements(explore_xs);
            setCurrentSection("explore");
        } else {
            toggleElements(navigate_xs);
            setCurrentSection("navigate");
        }
    } else if (md) {
        toggleElements(navigate_md);
        setCurrentSection("navigate");
    }
    else {
        toggleElements(navigate_md);
        setCurrentSection("navigate");
    }
});
```

---

#### *Tablet*

Tested on iPad simulator (Chrome)

---


#### *Desktop*

Tested on Chrome, Safari, Firefox

---

**PROBLEM**

Autocomplete input select dropdown behind navbar

**FIX**

Adjust z-index.

---
