# ![Protractor Workshop](protractor-logo-large.png)

> ### Protractor workshop that covers useful patterns when creating end to end tests as well as covering promises

The workshop makes use of two forked projects - [Angular Realworld Example App](https://github.com/hughleo/angular-realworld-example-app) for the Angular UI and a spring boot backend for the API - [Springboot Realworld Example App](https://github.com/hughleo/spring-boot-realworld-example-app)


# Pre-requisites
* Java 8
* Gradle
* Node 8 or above
* NPM
* Visual Studio Code (or other IDE for Node)
* Git

# Getting started

## NOTICE: IF you are behind a corporate proxy, please see section below to allow the following installs and builds to work

### For the Angular UI:
On the command line:-  
* Install the Angular CLI: `npm install -g @angular/cli`  
* Clone or download [Angular Realworld Example App](https://github.com/hughleo/angular-realworld-example-app)  
* Then start the application  
* `cd angular-realworld-example-app`
* `npm install`  
* `ng serve`  
* Navigate to `http://localhost:4200/`

If this doesn't work, perform the following steps:  
* Add `%USERPROFILE%\AppData\Roaming\npm` to the end of your Path  
* Then run `npm run ng serve`  

### For the backing API

* Clone or download [Springboot Realworld Example App](https://github.com/hughleo/spring-boot-realworld-example-app)
Then start the application:
* `cd spring-boot-realworld-example-app`  
* Mac: `./gradlew bootRun`
* Windows: `gradle bootRun`


## For protractor: 
* Install protractor globally: `npm install -g protractor`
* Run WebDriver manager update: `webdriver-manager update`

## Running your first test
 
* Sign up as a new user (at `http://localhost:4200/`) using a dummy email and password
* Add this email and password to params section of protractor.conf.js
* In command line, run `protractor protractor.conf.js`


## Proxy settings: 

If you're behind a proxy you may have to do set proxy information:

### NPM
* npm config set proxy http://username:password@proxy-server-url:port
* npm config set https-proxy http://username:password@proxy-server-url:port

### GRADLE

Create a gradle.properties file at top level of project with the values filled in for your proxy information and username and password.

`systemProp.http.proxyHost=proxy-server-url`  
`systemProp.http.proxyPort=port`  
`systemProp.http.proxyUser=username`  
`systemProp.http.proxyPassword=password`  
  
`systemProp.https.proxyHost=proxy-server-url`  
`systemProp.https.proxyPort=port`  
`systemProp.https.proxyUser=username`  
`systemProp.https.proxyPassword=password`  

### WEBDRIVER-MANAGER

`set HTTP_PROXY=http://proxy-server-url:port`   
`set HTTPS_PROXY=http://proxy-server-url:port`


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

