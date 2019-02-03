---
layout: post
title:      "My First Attempt at Writing Tests"
date:       2019-02-03 16:50:13 +0000
permalink:  my_first_attempt_at_writing_tests
---


As part of a recent code challenge I was encouraged to work with a technology that I had never used before. Instead of learning a new tool to build my app I decided to learn how to test my app. This turned out to be a rather optimistic endeavor as I had never written tests for any of my applications so I had to learn a new practice in addition to learning a new technology. 

My app is a front-end React app that pulls data from a third-party API, so I looked into tools typically used to test such things.  My search started directed me to the [Create React App Documentation](https://facebook.github.io/create-react-app/docs/running-tests) since testing is mentioned there.  As is so common with technology these days, there are many different tools available to get the job done and event the Create React App documentation provide several suggestions.  Fortunately, the common factor amongst them was Jest since it comes packaged with react-scripts (if you bootstrap your project with create-react-app).  Unfortunately, most folks don’t just use Jest, they typically also use at least one, if not several other libraries to assist them with the testing process.  And so began my adventure in trying to decide on the best route to take. 

I started with trying out Enzyme since there were many blog posts available as resources and because it was mentioned as a common option in the Create React App Documentation.   In order to best use the enzyme package you needed to install several other libraries as well. Specifically react-test-renderer and enzyme-adapt-react-16 (if you are using version 16 of React). To install all of these you can run: 

```
npm install --save enzyme enzyme-adapter-react-16 react-test-renderer
```

Enzyme requires that you configure an Adapter specific to the version of React you are using. You can set this up in every test file, or to make things easier, you can set this up in a setupTests.js file located in your src folder. 

```
// src/setupTests.js
import { configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

configure({ adapter: new Adapter() });
```

From here you need to determine how to organize your testing files and you component files.  There are several methods typically used to structure your testing files. Some folks make separate folders for each of their components and include the component and its test file in that oflder (Jest will look for any file in the src folder that has an extension of .test.js) or you can have all of your components in a component folder and create a `__test__` folder in your components folder and put all your tests there (Jest will look for any .js files in the` __test__` folders).  I started with the one folder per component method, but I didn’t care for it since the relative paths to my component files got rather lengthy, so I reorganized my files so all my components were in a components folder and the tests were in a `__test__` folder. 

Now the hard part…actually writing a test. Most of the blogs that I found recommended that you start with the small easy components and work your way up to the more complicated ones. I wasn’t sure how to test my smallest component at first so I started with one that was one level up and used the smallest component. The first problem I ran into was that all of my components require props. Since I’d seen that Flatiron mocked out test data I grabbed some data from the third-party API and plopped it in my setupTests.js file (making sure to export it) so that I could use that data where ever it was needed in my component testing.  

Now I had props to pass to my components in my tests, but how does one write a test in Enzyme.  I followed some blog posts and watched several videos and I was able to use Enzyme’s `shallow` and `mount` functions to render my components and use [Enzyme matchers](https://airbnb.io/enzyme/docs/api/ ) to grab certain parts of the render and then use [Jest matchers](https://jestjs.io/docs/en/using-matchers) to compare the render parts against the expected values.  PS – there are some great cheat sheets out there for [Enzyme](https://devhints.io/enzyme) and [Jest](https://github.com/sapegin/jest-cheat-sheet). 

I struggled with getting my first tests written and passing and the more research I did the more I I got the sense that Enzyme was no longer the golden child of testing out there in the React world. The new hotness, as of March of 2018 (when it was released) is the [react-testing-library]( https://github.com/kentcdodds/react-testing-library).  Kent C. Dobbs built this library to make testing more of a process of testing what a user would do, as opposed to testing implementation details. He has a ton of articles on best testing practices on his [blog]( https://blog.kentcdodds.com/tagged/testing).  Since I’d only written a few tests for a few components that were all very similar in behavior I decided to shrug off Enzyme and dig into React-testing-Library.

It is recommended that you install the react-testing-library with jest-dom:
```
npm install --save react-testing-library jest-dom
```

And in your scr/setupTests.js file you should configure the following:

```
import 'react-testing-library/cleanup-after-each';
import 'jest-dom/extend-expect';
```

The cleanup-after-each function cleans up the renders after each test and the jset-dom/extended-expect gives you access to some custom assertions. 

After setting up my project with react-testing-library I was still feeling very lost as to how to proceed with writing tests and I was getting frustrated and overwhelmed by the resources I had come across thus far so I splurged on a Pro Account with [Level Up Tutorials](https://www.leveluptutorials.com/pro) and spent the next day working my way through the videos on [React Testing for Beginners](https://www.leveluptutorials.com/store/products/tutorials/lut-dd026).  It was a great introduction to testing, the react-testing-library and jest-fetch-mock. I was able to rewrite my Enzyme tests for my second level components and figure out how to write tests for my base level components. 

I’m still stuck on how to write some of the tests for my more complicated components. But I’m going to continue to do research and I’m hoping that by reading through some of the Jest documentation and some of Kent’s blog posts that I’ll be able to flesh out my test suite.

