# Assignment 1: Oauth 2.0

We are going to program a very small web application that will be a very basic and reduced interface for GitHub. Basically it needs to:
* Authenticate the user via GitHub
* List all the repositories (public and private) of the authenticated user
* List all the issues in this repository 
* Create new issues in this repository

There will be a index.html page accessible by all users with links to the before mentioned functionalities and another one
to login bia GitHub. In addition when an user has already logged in his/her name will be shown in this page. 

### Repositories
When listing repositories you only need to show:
* id
* name
* full name
* whether it is private
* git url
* owner's name

### Issues
When listing issues you need to show:
* id
* title
* body
* state
* a list with the name of all labels
* the user's login
* a list with the name of all assignees
* full name of the repository it belongs to 

## Some help and information

### Oauth
Recall than in Oauth there are three different actors: 
* Client: your web application
* Server: gitHub
* Owner: the user on behalf of whom we are accessing repositories and issues

### Steps you need to do 
1. Register your application in GitHub and obtain the Client ID and the Client Secret: in your GitHub page, go to your 
profile, select settings, on the left go to "Oauth applications" under "Developer settings" label. 
    1. set the Authorization callback URL to your application (probable http://localhost:8080)
1. Provide with a url (maybe via a filter) for the user to authenticate and to authorize your application (the client to 
access the user's GitHub resources). This step will redirect your application to GitHub and back to your application (the
link you introduced in the former step)
    1. You can set the client properties in the application configuration file
    1. In the former step set the scope to: repo (it will access to read and **write** user's repos)
1. Once GitHub redirects the user is already authenticated and the spring security already stores all necessary tokens for the user 
1. You'll use the tokens to list repos and read/write issues


### Useful links:
* Spring Oauth tutorial https://spring.io/guides/tutorials/spring-boot-oauth2/ . I would execute and inspect the code for the following examples: simple, click and manual.
* Spring Oauth documentation (go to Oauth2 client section): https://projects.spring.io/spring-security-oauth/docs/oauth2.html
* API GitHub: https://developer.github.com/v3/
* API GitHub Gists https://developer.github.com/v3/gists/
* An example based on the "manual" from the first link. It authenticates with GitHub and obtains a list of all the authenticated user's repositories: https://github.com/DSI-T21617/GitHubOauth
* An example where the Oauth2RestTemplate is used only for authorization (not authentication - security): https://github.com/DSI-T21617/Ouath2AuthorizationFlow


## Base Code:
Follow the link in order to create your own copy of the code: 