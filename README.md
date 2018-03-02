# ![Protractor Workshop](protractor-logo-large.png)

> ### Protractor workshop that covers useful patterns when creating end to end tests as well as covering promises

The workshop makes use of two forked projects - [Angular Realworld Example App](https://github.com/hughleo/angular-realworld-example-app) for the Angular UI and a spring boot backend for the API - [Springboot Realworld Example App](https://github.com/hughleo/spring-boot-realworld-example-app)


# Pre-requisites
* Java 8
* Gradle
* Node 8
* NPM
* Visual Studio Code (or other IDE for Node)

# Getting started

* Clone or download [Angular Realworld Example App](https://github.com/hughleo/angular-realworld-example-app)
* Clone or download [Springboot Realworld Example App](https://github.com/hughleo/spring-boot-realworld-example-app)

## For the Spring Boot app:

* Mac: ./gradlew bootRun
* Windows: gradlew bootRun

## For the Angular UI:

Make sure you have the [Angular CLI](https://github.com/angular/angular-cli#installation) installed globally, then run `npm install` to resolve all dependencies (might take a minute).

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. 

## Proxy settings: 

If you're behind a proxy you may have to do set proxy information:

### NPM
* npm config set proxy http://username:password@proxy-server-url:port
* npm config set https-proxy http://username:password@proxy-server-url:port

### GRADLE

* Create a gradle.properties file with:

* systemProp.http.proxyHost=proxy-server-url
* systemProp.http.proxyPort=port
* systemProp.http.proxyUser=username
* systemProp.http.proxyPassword=password

* systemProp.https.proxyHost=proxy-server-url
* systemProp.https.proxyPort=port
* systemProp.https.proxyUser=username
* systemProp.https.proxyPassword=password

## Running your first test
 
* Open `http://localhost:4200/`and Sign up as a new user, using pretend email and password
* Add this email and password to params section of protractor.conf.js
* in command line, run protractor protractor.conf.js


## Functionality overview

The example application is a social blogging site (i.e. a Medium.com clone) called "Conduit". 

**The general page breakdown looks like this:**

- Home page (URL: /#/ )
    - List of tags
    - List of articles pulled from either Feed, Global, or by Tag
    - Pagination for list of articles
- Sign in/Sign up pages (URL: /#/login, /#/register )
    - Uses JWT (store the token in localStorage)
    - Authentication can be easily switched to session/cookie based
- Settings page (URL: /#/settings )
- Editor page to create/edit articles (URL: /#/editor, /#/editor/article-slug-here )
- Article page (URL: /#/article/article-slug-here )
    - Delete article button (only shown to article's author)
    - Render markdown from server client side
    - Comments section at bottom of page
    - Delete comment button (only shown to comment's author)
- Profile page (URL: /#/profile/:username, /#/profile/:username/favorites )
    - Show basic user info
    - List of articles populated from author's created articles or author's favorited articles


<br />

