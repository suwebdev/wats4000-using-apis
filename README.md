# Using APIs to Provide Data

> Practicing using APIs to retreive data in an application.

It is very common to use third-party data APIs to enhance our applications. It
is also common to build our own API services and then reveal even custom logic
and features through a standardized API interface. This type of application
architecture has become very popular online, and it is a fundamental technique
in building website and web-based applications.

This project is designed to practice creating simple API requests from within a
Vue.js application. We will make requests and use them to populate information
for our users. For this project, we will make requests to the [Datamuse API](http://www.datamuse.com/api/),
which is a wonderful, free service useful for finding the word we need.

This project is designed to go alongside the content and instructions in the
[Practical JavaScript 2: Building Applications](https://suwebdev.github.io/WATS-4000-gitbook/using-api-data/) book.

## Project Goals
The goal for this project is to make the "Rhymesaurus" functional. This feature
allows a user to search for words that rhyme with something and have to do with
a specific topic. The user can fill in both fields to specify the parameters of
their search, and then words are returned. If no words are found, then the user
is advised of that failure and can alter their search parameters.

Once we have completed that, we will be challenged to create another component
from scratch that performs a different kind of search.

## Basic Requirements
In order to successfully complete this project, we must fulfill the following
requirements. The requirements below are organized according to the file we will
modify to fulfill them.

**`/src/components/Rhymesaurus.vue`**

`<template>`

* Set up an event handler to trigger the `findWords` method when the `form` is submitted
* Use a conditional to control the display of the `ul.results` element so it only displays when results are ready to be shown
* Use a loop to process all of the results into list items
    * Output the word in each list item
    * Output the score for each word in each list item
* Use a conditional to control the display of the `.no-results` message, which should only show when the user has attempted a search and no words have been found
* Use a conditional to control the display of the `ul.errors` element so it only displays when there are errors ready to be shown
* Use a loop to process all of the errors and display them for the user

`<script>`

* Import axios for use in the component logic
* Create a method called `findWords` (don't neglect to add the `methods` attribute to this component)
* Within the `findWords` method, create an `axios.get()` statement that will make a request to `https://api.datamuse.com/words`
    * Define the `params` for `ml` (which should map to the `phrase`) and `rel_rhy` (which should map to the `rhyme`)
    * Define a `then` clause that sets the component's `results` value to the value of `response.data`
    * Define a `catch` clause that will add any error to the `errors` array in the component

**`/src/components/NewComponent.vue`**

(Please do not actually name the new component `NewComponent.vue`. This name is only being used for reference here. Name the component according to whatever feature it provides.)

* Create a new component (use the boilerplate component code, or copy the component you just created)
* Refer to the Datamuse API documentation to determine a way to modify your code to provide an alternative way to find words (e.g. "sounds like", "related to", "adjectives that go with a word", "words that often follow a word", etc.).
* Implement a similar interface to perform this new search
    * Create the necessary template to allow the user to enter at least one search parameter
    * Create the necessary method to handle the form submission and API request
* Implement the proper template elements to output the results to the user
    * Show all relevant results returned by the API
    * Show all errors to the user
    * Show a message when no results have been found, so the user knows the system is working even though the data is not there

**`/src/router/index.js`**

* Add the new component to the import statements in the router definitions file
* Add the new route to the router definitions list (use a sensible URL and name for it)

**both `/src/compnents/Rhymesaurus.vue` and `/src/components/NewComponent.vue`**

* Add navigation elements to provide links between the two search pages
* Use proper `router-link` tags to create links
* Allow the user to easily switch between the two pages in the application.

## Stretch Goals
If you are looking for additional challenges with this project, consider working
on the following goals.

* Create a similar application using a different API. ([Find suggested APIs for experimenting with here](https://suwebdev.github.io/WATS-4000-gitbook/appendices/appendix-b-api-suggestions.html))
* Add a second API to this application and mingle the results in some interesting way
* Use the "score" data from the API to modify the visual presentation of the words to indicate which ones are the best matches for the user's search parameters
* Use the data returned from the API to modify the appearance or interface in some other way

## Instructions for working with this application

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run serve

# build for production with minification
npm run build

```

**Note:** This application has been configured to build files to the `/docs` directory, making it compatible with the "Serve from `master` `/docs` directory" setting for GitHub Pages. Please adjust your GH Pages settings accordingly on your repository settings page.

For detailed explanation on how Vue works, check out the [guide](https://cli.vuejs.org/guide/) and [docs for vue-loader](https://cli.vuejs.org/config/#css-loaderoptions).

## Credits
This project makes use of the [Datamuse API](http://www.datamuse.com/api/), which is a wonderful, free API service that you should support.