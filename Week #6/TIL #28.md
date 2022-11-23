# Today-I-Learn #28
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 23rd, 2022

### Q1. There are other ways besides having the conditional evaluate to `false` to break or ignore the loop. What’s the difference between loop control methods, and give the example!

There are other ways besides having the conditional evaluate to `false` to break or ignore the loop. There are `break` and `continue`.

- `break` statement
    
    A syntax to **break the loop regardless of condition.**
    
    ```js
    for (let i = 0; i < 5; i++) {
    	if (i === 2) break;
    
    	console.log(i);
    }
    
    // Print: 0
    // 1
    ```
    

- `continue` statement
    
    **Aborts the statement regardless of the condition and executes the next step,** the increment statement.
    
    ```js
    for (let i = 0; i < 5; i++) {
    	if (i === 2) continue;
    
    	console.log(i);
    }
    
    // Print: 0
    // 1
    // 3
    // 4
    ```
    

### Q2. How to move a commit to another branch in git?

Let's say we have made a commit a1b2c3d on the branch feature-a, and we haven't yet made a feature-b branch. As long as we haven’t pushed the commit, the way to undo a commit to another branch is by using

```
git checkout branchname
```

Then make sure you are on the right branch feature-b (may not be necessary if you just created it), and cherry pick this commit into that branch to add just that commit to feature-b

```
git checkout feature-b
git cherry-pick a1b2c3d
```

And finally let's reset feature-a branch back to the previous commit hash (say z1b2c3d). Using git reset --hard will remove all the commit referencing the changes, and all the changes themselves, from feature-a branch, while leaving that commit on feature-b:

```
git checkout feature-a
git reset --hard z1b2c3d
```

This can only be done if the commits is not pushed to origin branch yet.

### Q3. What are the differences between Mongoose Schema vs Mongoose Model?

A Mongoose model is a wrapper on the Mongoose schema. A Mongoose schema defines the structure of the document, default values, validators, etc., whereas a Mongoose model provides an interface to the database for creating, querying, updating, deleting records, etc.

### Q4. What is the difference between a framework and a library?

Library is a collection of reusable functions used by computer programs meaning the resources which you can reuse which may include classes, subroutines, pre-compiled code, message templates, etc.

Framework is a piece of code that dictates how the project should be structured and run. It simply mandates the architecture of your project like defining the design parameters of an application so 
that you can focus on the specifics of the project, thereby emphasizing on reusability of design rather than reusability of code.

By comparison The Library and Framework can be written down as this list :

![image](https://user-images.githubusercontent.com/62550785/203607197-a2a3e2b9-6599-49ac-b567-22e250229d3b.png)

In more simple diagram, Library and Framework can be drawn like this diagram :

![image](https://user-images.githubusercontent.com/62550785/203607227-44e5407f-cc65-40e1-827b-e35bf47d67e3.png)

The conclusion is Framework is reusable code that can be modify by the user , work by making call request to Framework, and provide guide or standarization in deploy and building app. Beside that, Library is a reusable function that has been made, work by calling itself in the code, and important to link program or bind  process.

Q5. What’s the difference between `git pull` and `git pull --rebase` ? And when we use `git pull --rebase` ?

- **The difference:**
    - **`git pull`** = **`git fetch`** + **`git merge`** against tracking upstream branch.
    - **`git pull --rebase`** = **`git fetch`** + **`git rebase`** against tracking upstream branch.
    
    - **The difference between `git merge` and `git rebase`**
        1. `git merge`
            - Suppose you have a main branch which contains the code changes for your application.
            - Now there are multiple bugs reported on this main branch, so each bug is assigned to a different developer. Now we assign a different branch to each developer so they can continue with the bug fix changes while the main branch continues to have stable code.
            - Once the developer has fixed and tested the changes then they will switch to the main branch and then merge their branch with main branch. This would merge all the commits which were done in the developer branch
            
            ![image](https://user-images.githubusercontent.com/62550785/203607256-8a77c8d6-06e2-4ef2-8949-e95acc2550b5.png)
            
            > ***In this example diagram as you can see, the developer has created a new branch by using git checkout -b feature. in the feature branch he does 2 commits and then now since he knows the bug has been fixed so he switches to main branch and merge his changes.***
            
            
        2. `git rebase`
            - The main reason we do a `git pull --rebase` over git pull is because **it avoids loops** in the project history.
            - For instance, the master branch has had many changes since you began working on your feature branch. You want to acquire the newest updates from the master branch to your local branch while maintaining a clean history of your branch to appear as you have been working off the latest master branch.
            - Git rebase guarantees a clean merge between your feature branch back into the master branch without keeping commit history.
            - Why then do we need a clean history? The importance of a clean history becomes evident when carrying out Git operations to explore the foundation of a regression.
            - Quite literally, the process of rebasing is a way of rewriting the history of a branch by moving it to a new “base” commit.
            
            ![image](https://user-images.githubusercontent.com/62550785/203607306-436d4558-4523-4b3b-a184-8628222ce4fc.png)
            
    - **When we use `git pull --rebase`?**
        1. When multiple individuals are working on the same branch
        2. When you want to crush multiple commits
        3. When you want to overwrite the history.
        4. When you want to repeat each commit and add the changes.

> ***If you wanna learn more about `git`, just check link: [https://www.golinuxcloud.com/git-pull-vs-git-pull-rebase/#How_git_rebase_works](https://www.golinuxcloud.com/git-pull-vs-git-pull-rebase/#How_git_rebase_works)***
