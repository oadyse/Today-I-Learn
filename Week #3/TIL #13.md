# Today-I-Learn #13
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 2nd, 2022

## What did I learn today ?

- Today I learn about Redux again, and re-read about the Team Task before.
- We had a mentoring session with Mr. Adhitya
- Today I finished my Personal Task
- So today I had a problem about my deploy.
  
  
  It turn error like this:
  
  ```
  -----> Building on the Heroku-20 stack
  -----> Determining which buildpack to use for this app
  -----> Node.js app detected
  -----> Build failed
   !     Two different lockfiles found: package-lock.json and yarn.lock
         Both npm and yarn have created lockfiles for this application,
         but only one can be used to install dependencies. Installing
         dependencies using the wrong package manager can result in missing
         packages or subtle bugs in production.
         - To use npm to install your application's dependencies please delete
           the yarn.lock file.
           $ git rm yarn.lock
         - To use yarn to install your application's dependencies please delete
           the package-lock.json file.
           $ git rm package-lock.json

         https://help.heroku.com/0KU2EM53
   !     Push rejected, failed to compile Node.js app.
   !     Push failed
  ```
  
  And I solved it with delete my package-lock.json and deploy it again.
  Voilaaa, it solved.

## What did I do well ?

- I finished my personal task and deploy it to heroku.
- I finally could deployed my app to heroku. I asked Mr. Adhitya before about it, and it solved.

## What needs to improve?

### Problem

- Even though, I finished my personal task but still I am confusing sometimes about Redux.

### Action

- I need learn more and more about Redux and material this week

## Documentation

- We had a discussion about our personal task, actually previously we had a mentoring session with Mr. Adhitya, but I forgot to capture it.

  ![image](https://user-images.githubusercontent.com/62550785/199544032-21e1fdc6-f8d5-4dc7-9d5c-4c8edd94594f.png)
  
- You can see my task in link here : [my-todolist-2-sarieka](http://my-todo-list2-sarieka.herokuapp.com/)

  ![image](https://user-images.githubusercontent.com/62550785/199548388-53a5b5e3-22c0-448a-88eb-6a8ea36ff390.png)

