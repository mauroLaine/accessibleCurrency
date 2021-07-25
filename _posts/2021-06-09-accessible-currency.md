---
layout: post
title: Accessible Currency
excerpt_separator:  <!--more-->
---

### Introduction

This project aims to provide a tool for BLV people to improve their interaction with physical currency via an Android mobile app. Moreover, it is designed to support multiple languages in order to provide inclusion to those who speak another language different from English. 

There are physical devices in the market designed to address this issue; they are cards or iBill that read currency bills. Nonetheless, these devices have some limitations, e.g., they only can recognize bills, they recognize only currency in good shape, some of them are expensive and usually difficult to find. 

On the other hand, there are mobile apps available in Google Play that are detecting currency. Nonetheless, some of these apps use landscape mode, making them difficult to navigate for BLV people. Some others are not free, and according to user comments, their level of accuracy while detecting the currency is poor.

### Related Work

This project was based principally on references related to BLV people using paper money and documentation of BLV people and smartphone experiences. 

<a href="https://blindcoincollector.com/2019/02/18/how-blind-people-identify-paper-money/" style="color: #007dac;color: hsl(196.2,100%,33.7%)">How Blind People Identify Paper Money</a> is an excellent reference to hear experiences from BLV people. In this source, the team learned the behavior expected from the final user when the app would be used.

<a href="https://www.researchgate.net/profile/Asm-Anam-2/publication/262399684_Accessibility_in_smartphone_applications_What_do_we_learn_from_reviews/links/55ef112508ae0af8ee1b0a46/Accessibility-in-smartphone-applications-What-do-we-learn-from-reviews.pdf" style="color: #007dac;color: hsl(196.2,100%,33.7%)">Accessibility in Smartphone Applications: What Do We Learn from Reviews?</a> was very useful since it provided a more extended context of the usage of smartphones by BLV people.

### Solution

In order to find the best approach for currency recognition, the team experimented with several potential solutions. The first approach was using text recognition to identify the bills and coins. The results from this experiment were different than the ones expected. For this case, the ML read random text on the bills, and for the coins, it did not recognize it in many cases since this text was too small for the phone's camera.

The second approach the team tried was to use image labeling, which worked better than text recognition. However, the challenge this time was to identify the value of each currency since the model only recognized bills and coins but not values on any of them. In order to achieve the recognition of every bill and coin value, the team implemented a customized ML model built with a plethora of images of currencies. This was the solution that fit the best, and therefore, the team moved forward and implemented it.

For supporting multiple languages, we used localization tools provided by Android; this allows us to use the same UI with several languages and isolate the captions in single XML files.
Finally, we have added a feature called Wallet, which allows the user to sum the amount of money scanned, this feature does that by storing the value of each currency scanned and providing the total amount of scanned money to the user via Talk Back. 

### Validation

For the validation part, the app was tested in real conditions using bills and coins. These test cases were to determine the approximate amount of photos we have to include in the model. Additionally, they help to define the user experience implemented in the app.

Moreover, the team used Accessibility Scanner, an app to validate the mobile accessibility in our app. Accessibility Scanner analyzed all the views the Accessible Currency app has, and after an evaluation of the UX and UI, no suggestions were found.

### Learnings and future work

In this project, we learned the implementation of ML models in mobile applications. Furthermore, exploring different types of models allowed us to get familiar with some other parameters that have to be taken into account when designing ML systems. E.g., for image labeling, the accuracy of the prediction might depend on the number of photos taken and added into the model. Moreover, we noticed that the more hours of training with different data sources and many examples, the more the error percentage gets minimized. Finally, another highlight is that when working with cameras embedded in mobile devices, the light in the room could affect the recognition if not enough data has been provided. 

For future work, even when this first version intends to provide the fundamental elements to help BLV people with currency recognition, There is a plethora of work to be done, for example, the support of more languages, the training of more photos of currency, and complete sets of currencies from other countries, and finally the team considers that the best feedback will come from the users in the Google Play Store comments.


