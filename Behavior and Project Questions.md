# Behavior and Project Questions

### Your role at last company
My last company I worked for is Pixta Vietnam. At Pixta Vietnam, I joined it as Backend Developer, working mainly on Ruby, Rails and AWS. 
After about 1 year, Pixta have a new project, and also open a new position so I take that oppoturnity and changed my role to Front-end Developer.
As a FE developer, I working mainly on ReactJS, and NextJS. The more I work with FE, the more I interested on it. After 1 year, this project came to adverstizing state, where the workload is not much. Also, the environment of Pixta don't have much FE engineers, mostly is BE engineers, so my learning curve/speed on FE start going down. That why I'm looking for another oppoturnity.

### Why do you change from Back-end to Front-end
There are few reasons that made this decision. Personally, I always looking for challenges, to develop myself and growth at a faster pace. Also, I love the felling when you can solved challenging problem. So, at that time, changing to new fields is the most challenging challenge for me. Plus, FE in the last few years growing super fast, it have many new technologies, tools, frameworks, and it still growing. Compare to FE, BE is quite mature now, you can pickup any framework and then make a same product with that framework.

So, with all these reasons, I decided to take the challenge to become a FE developer.
And yeah, I'm happy because I take up that challenge. Learning FE and do the work in FE is very enjoyable and give me a lot of new knowledge. The more I work in FE, the more I interested on it.

### What I learn by transaction from Back-end to Front-end
> How I switched from building products for frontend developers to building products for users.

Transitioning from Back-End to Front-End development is not easy. I got used to the structure of back-end stuff where you usually build the data structures, writing tests, database tables, and creating API endpoints for Front-End consumption.

To date, these are my experiences while I transition from Back-End to Front-End developer:
- It’s all about User Interface and User Experience
- It makes you think of “UI-first” and how your app flows when starting your project 
- It lets you think of how to improve UI reusability
- It’s all about Browser-side performance and client-side optimizations
- You learn how to build Responsive Web Pages
- You learn how to look at SEO as well
- You learn to be good at CSS
- You want to be a designer

### Tell me about your last project
It's a stock photo website, using latest technology.

### Problem on your project - Image grid
https://helix-moth-20b.notion.site/Row-Wise-Grids-1b82573fabb346b0a6202cbe72ebb0b3

### Problem on your project - Speed optimization
- Async - Defer 3rd parties lib - Remove render-blocking js: https://web.dev/efficiently-load-third-party-javascript/
Async script:
![image](https://user-images.githubusercontent.com/30380214/128219909-73aca43b-63f6-488a-b26b-202da9e35e6f.png)
Defer script:
![image](https://user-images.githubusercontent.com/30380214/128219938-eb2bba81-62ab-4b65-ac92-092fb1a8ca79.png)
Use async if it's important to have the script run earlier in the loading process.
Use defer for less critical resources. A video player that's below-the-fold, for example.

- Image optimization - dynamic sizes + src-set + lazyload + correct image format
Don't save images larger than their display size.
Save multiple sizes for each image and use the srcset attribute to enable the browser to choose the smallest. The w value tells the browser the width of each version:
```html
<img src="small.jpg"
     srcset="small.jpg 500w,
             medium.jpg 1000w,
             large.jpg 1500w"
     alt="…">
```
- Static site generation
- Remove unused library - Tree shaking ⇒ Minify CSS, JavaScript, and HTML
- Caching strategies - CDN
- Monitor via Datadog - RUM - Realtime user monitoring
- Reduce number of requests - code spliting
- Consider Using Prefetching - AKA static site, server side rendering Next JS
