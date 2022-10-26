# Today-I-Learn #7

October 25th, 2022

## Intro

Actually, Today is kinda tough day for me. Cus i am not feel not that good today.
But I'll try to joined the ZEP with my teammates. Even though I can't active like usually,
I am just listening what my teammates said.

And then, I asked some question to Mentor what was my problem with react. 
Why I couldn't use *yard* syntax for create my react app.
And the problem is I have space on my device's User name.
But I told him, that still I can run with other syntax.

And we were doing some questions for group-task about Javascript. I write it down:




### 1. We usually use ``` ref ``` to approach to DOM in react. Why do we use ``` ref ``` instead of ``` document.getElementsByClassName``` ?

ReactJS Framework works in different way than normal JavaScript or jQuery. JavaScript and jQuery normally only run when the user does something and call functions. After that JavaScript will execute that function based on what user put in the parameters. The situation is different with ReactJS Framework, React will keep updating new user interface whenever the user does something and change the state.

To have better understanding, we must learn about ReactJS lifecycle first. There are 3 cycles:

- Mount, React will render whole code and return JSx from the component.
- Update, whenever user does something, like pressing a button, write a letter to an input box, move some element, react will consider it as changing state and render a new UI right away.
- Un-Mount, this phase for deleting unnecessary part and managing memory.

if we use getElementsByClassName, it may cause some error since React may re-rendering pages with its own timing and JavaScript will has different timing.




### 2. Explain SPA and MPA.
![image](https://user-images.githubusercontent.com/62550785/197924695-28960aad-beaf-455a-a462-37361a29dbb1.png)

- **SPA (Single Page Application)**

A SPA is an application that allows you to work inside a browser and does not require any reload for the page when a user is using it. Many of the application that we use every day are SPA, for example Navigation apps, Social Media, or Email Providers.

SPAs, due to the presence of their HTML shells, can easily be converted to progressive web applications (PWA) leading to a more seamless experience for the user. Likewise, their JavaScript-dependent shell also allows it to be able to load preloaded pages while offline. Known as offline caching, this allows users to never lose track of their data while on the app. The SPA only needs you to send one request, store all data, and then can freely access all of this data while offline.

- **MPA (Multi-Page Application)**

Multi-page applications, or MPAs, request rendering each time for a new page from the server in the browser. They’re perfect for applications larger than SPAs, and due to the amount of content, they have different levels of UI. They are often known as the “traditional” way of app development, and though there are multiple levels of UI, this has recently been resolved due to the developments of AJAX.

AJAX allows the transfer of a large amount of complex data between the servers and browsers, however; this also brings some problems. With its ability to transfer data, there’s a new layer of complexity that often challenges JavaScript developers.
