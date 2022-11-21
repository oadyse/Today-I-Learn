# Today-I-Learn #26
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 21st, 2022

## Introduction
  
  Today is the first day to learn Node.js and Express.js as a framework of Node.js. 
  Hope I can get to learn this quickly and can finish my personal task on time.

## What I have done today?

  - Today We had a session with Ms. Eunseo, she asked how was our team, and asked about the material too, etc.
  - And then we had little bit mentoring session, We had some qna on here.
  - We finished team task questions.

### 1. Why did `for...in` & `for...of` was made although there is for loop already? In what standard do we choose to use those?

   > `for ... in` and `for ... of` are kind of looping in Javascript. But what makes different between a normal for? 
   > ***That’s because this method is loop through the object.***
   
   - **`for ... in`**
      
      > When we used it?
      
        We used `for ... in`  when the repetition of index/key elements in objects.
        
      > Interface or Structure
        
        ```js
        for (variable declaration of iterable) {
          // Statement
        }
        ```
        
      > Example:
        
        ```js
        const team6 = ['Reyvido', 'Deny', 'Ibnu', 'Eka'];

        for (const member of team6) {
          console.log(member);
        }

        // Print: 'Reyvido'
        // 'Deny'
        // 'Ibnu'
        // 'Eka'
        ```
      
   - **`for ... of`**

      > When we used it?
        
        We used `for ... of`  to repetition of index/key elements in objects.
        
      > Interface or Structure
        
        ```js
        for (variable declaration in iterable object) {
          // Statement
        }
        ```
        
      > Example:
        
        ```js
        const team6 = ['Reyvido', 'Deny', 'Ibnu', 'Eka'];

        for (const member in team6) {
          console.log(member);
        }

        // Print: 0
        // 1
        // 2
        // 3
        ```
    
### 2. What is the difference between an Array-Like Object and Array in JavaScript? What process do we have to go through to make changes to each components of the Array-Like Object?

   > **Array**
   
   - Array is a special variable where you can put several items in it. 
      It uses automatic index with number starting from 0 without any negative. 
      It will use square bracket `[]` and comma to separate other items inside the array.
   - Example:
      
      ```js
      const my_array = ['item_one','item_two','item_three']
      ```
      
   > **Array-like Object**
   
   - Array-like object is also an object. Before we talk about array-like object, we must know what object is. 
      Object is similar with array, but it has flexible index or key name. Object also use parentheses `{}`.
   - Example:
      
      ```js
      const my_object = {key_one:'value_one', key_two:'value_two', key_three:'value_three'}
      ```
    
### 3. What is the difference between put in RestAPI and patch? In what circumstances do we use them? 
    
   | PUT | PATCH |
   | --- | --- |
   | PUT is a method of modifying resource where the client sends data that updates the entire resource . | PATCH is a method of modifying resources where the client sends partial data that is to be updated without modifying the entire data. |
   | In a PUT request, the enclosed entity is considered to be a modified version of the resource stored on the origin server, and the client is requesting that the stored version be replaced | With PATCH, however, the enclosed entity contains a set of instructions describing how a resource currently residing on the origin server should be modified to produce a new version. |
   | HTTP PUT is said to be idempotent, So if you send retry a request multiple times, that should be equivalent to a single request modification | HTTP PATCH is basically said to be non-idempotent. So if you retry the request N times, you will end up having N resources with N different URIs created on the server. |
   | It has High Bandwidth | Since Only data that need to be modified if send in the request body as a payload , It has Low Bandwidth |
    
### 4. Let’s write MongoDB schema. Pretend there is a service where a registered user writes posts. You will see the title, writer name and more on the page. How should each model should look like? How should we import mongoose data in API that brings in the list of posts?

   If we want to make a MongoDB schema, where the registerd user are able to write a post, 
   which include the title, writer name, etc., the example would look like this:
   
   ```js
    // :id is all articles with all ids
    router.post('/:id', function (req, res) {
      let comment = {};
      comment.body = req.body.body;
      comment.user = req.user;
      comment.date = new Date(Date.now()).toDateString();

      // Express validator
      req.checkBody('body').len(5, 100);

      let errors = [];
      errors = req.validationErrors();

      if(errors) {
        Article.findById(req.params.id, function (err, article) {
          if(err)throw err;
          req.flash('danger', 'Body minimum length is 5 and maximum 100!');
          res.redirect('/articles/'+article.id);
        });
      } else {
        Article.findById(req.params.id, function (err, article) {
          if(err)throw err;
         article.comments.push({'body':comment.body,'user':comment.user,'date':comment.date});
          article.save(function (err) {
            if (err) {
              throw err;
            }else {
              req.flash('success', 'Comment added!');
              res.redirect('/articles/'+article.id);
            }
          });
        });
      }
    });
   ```
   
 ## Documentation for today
 
    ![Screenshot (217)](https://user-images.githubusercontent.com/62550785/203102679-c6ca0c37-141b-4df4-8420-d46395a1c90c.png)
