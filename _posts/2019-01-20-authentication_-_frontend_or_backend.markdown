---
layout: post
title:      "Authentication  - Frontend or Backend?"
date:       2019-01-20 21:21:09 +0000
permalink:  authentication_-_frontend_or_backend
---


I was asked in an interview this past week how I set up my Authentication on my applications – was it front-end or back-end? I was confused by this question since I thought that authentication was always handled just on the back-end and that authorization was typically handled by the front-end (based on the session cookie in the browser).  After reviewing some articles on the topic I found that handling authentication on the back-end is the traditional way of dealing with Authentication, but you can also handle it on the front-end.

For my Rails application, authentication is handled by the controllers on the server-side of the app.  The Sessions Controller validates the username and password and then sets the server-side session.  The Application Controller then determines if a user is logged-in based on whether or not the session has been set (and to which user it has been set).  And then the other controllers in the application (Users and Expenses ) require that the user be logged in (in most cases) in order to access various controller actions.  

My React application handles Authentication in a slightly different manner. The user logs in and the Sessions Controller still validates the username and password, but instead of setting a server-side session, it issues a JWT for that user id and passes it back to the front-end.  The front-end then stores this information (my app stores it in sessionStorage) and includes it in the Authorization Header of each request back to the server.  For each request that requires authentication, the Application Controller checks to see if a user is logged in by checking the header of the request for the JWT.  In this manner, authentication is achieved without any server-side state. 

It appears that a another approach for the React app would be to store the JWT that the back-end provides in two separate cookies and then have a thin-stateless authentication layer put them back together before sending along the request to the server. This layer allows us to update the timeout of the Authentication token  (if that is a requirement) and can also prevents Cross Site Request Forgery (CSRF) -  see more details on [this website]( https://medium.com/lightrail/getting-token-authentication-right-in-a-stateless-single-page-application-57d0c6474e3). 

* [More info on the difference between Local Storage, Session Storage and Cookies](https://scotch.io/@PratyushB/local-storage-vs-session-storage-vs-cookie) 

**Additional Resources:**
* [The Easiest Way to Add Authentication to Any App](https://scotch.io/tutorials/the-easiest-way-to-add-authentication-to-any-app)
* [Client vs. Server OAuth Flows with REST APIs](https://yeti.co/blog/client-vs-server-oauth-flows-with-rest-apis/)
* [Token Based Authentication for Single Page Apps (SPAs)](https://stormpath.com/blog/token-auth-spa)


