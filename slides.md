## Rendering on the web

Stefan Schwartze
---



### Hi I am Stefan
Senior Software Developer @Sevenval
Berlin Office, 3rd floor
I like JavaScript
I talk about some rendering on the web
Note:
* I mostly work on frontends    
* JavaScript is perfect because it runs almost anywhere
---

### Site loading
Problem
   1. Visit site
   2. loading
   3. Site rendering (10 minutes later...)
Note:
* Low network connection
* The loading indicator comes early, the interactivity really late
---

### What has happened?
Client side rendering
Note:
* Website is developed with JavaScript (React)
---

### How to solve?
Serverside rendering
---

### Is it only black or white?
---

### No, let's mix!
---

### Static-/ Prerendering
---

### Rehydration
---

### Ok, but how doing that?
---

### Introducing Next.js

* Framework for React
* Flexibility for rendering possibilites
Note:
* Other possibilities: Vue with Nuxt, Angular with Angular Universal (etc)
* There are a lot of things to consider, Next.js solves them for us
----

### Render per-page
----

### Flexible output
* Static
* Lambda
* Server Function
----

### Comparing One-to-One
----

### Testing a landingpage of a recent project
----

### Results
---

### When render on the server?
----

### When not render on the server?
----

### Anyhow: Stay flexible!
* Static pre-rendering for landingpages
* For non-SEO pages with dynamic content partly render on server and then request additional content from client (e.g. Dashboards)
* For pages with SEO and dynamic data relevance, render on server and hardly cache em'!
Note:
----

### Thx
---

### Sources

- [Rendering on the web](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
- [Server-side vs client-side rendering in React apps](https://async-await.com/article/server-side-vs-client-side-rendering-in-react-apps)
- [The Benefits of Server Side Rendering Over Client Side Rendering](https://medium.com/walmartlabs/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8)
---






## Terminology
----

- **TTFB**: Time to First Byte - seen as the time between clicking a link and the first bit of content coming in.
----
- **FP**: First Paint - the first time any pixel becomes visible to the user.
----
- **FCP**: First Contentful Paint - the time when requested content (article body, etc) becomes visible.
----
- **TTI**: Time To Interactive - the time at which a page becomes interactive (events wired up, etc).
---

## Types of rendering
----


- **CSR**: **C**lient-**S**ide **R**endering - rendering an app in a browser, generally using the DOM.
----


![Client-side Rendering performance](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/client-rendering-tti.png)
Note:
* Large bundles tend to long loading times
* Heavy code splitting required  
----


- **SSR**:
**S**erver-**S**ide **R**endering - rendering a client-side or universal app to HTML on the server.
----


![Server-Rendering](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/server-rendering-tti.png)
Note:
* Fast FP and FCP --> leads to fast TTI
* Disadvantage: takes time until site arrives in client (late TTFB)
* React/Next.js | Vue with nuxt | Angular with Universal
----


### Is it all black or white?


- **Static- /Prerendering**: running a client-side application at build time to capture its initial state as static HTML.
----
![Static- /Prerendering](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/static-rendering-tti.png)
Note:
* Perfect for relative static sites
* Preact has pre-rendering included, Next.js too
* Netflix implemented it for landingpages
----


- **Rehydration**: “booting up” JavaScript views on the client such that they reuse the server-rendered HTML’s DOM tree and data.
----


![Structure of a re-hydrated app](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/html.png)
----


![Rehydration](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/rehydration-tti.png)
----


**Problem**: generally double the work but still client-side blocked rendering
----


- **Streaming serverside rendering**: Send HTML in chunks
-> fast **FP** and **FCP**
-> React uses [renderToNodeStream()](https://reactjs.org/docs/react-dom-server.html#rendertonodestream) and **hydrate()**
---

## Theoretical benefit
----


![CSR](https://cdn-images-1.medium.com/max/2000/1*CRiH0hUGoS3aoZaIY4H2yg.png)
----


![SSR](https://cdn-images-1.medium.com/max/2000/1*jJkEQpgZ8waQ5P-W5lhxuQ.png)
---

## Comparing One-to-One
----

### Setup
- React / Next / Express
[CSR](https://ssr-csr.builderbook.org/csr) | [SSR](https://ssr-csr.builderbook.org/ssr)
----

### Results
- HTML is larger for SSR<!-- .element: class="fragment" -->
- Smaller TTFB and earlier FP for CSR<!-- .element: class="fragment" -->
- No advantages for SSR vs CSR<!-- .element: class="fragment" -->
----

### But what about reality?
[Walmart](https://medium.com/walmartlabs/the-benefits-of-server-side-rendering-over-client-side-rendering-5d07ff2cefe8) made 3 A/B tests for different pages
----
![Walmart](https://cdn-images-1.medium.com/max/2400/0*-EWG5MXBIo-D_ug3.)
---


## When render on the server?
----


- Slow network<!-- .element: class="fragment" -->
- Slow devices<!-- .element: class="fragment" -->
- Application must work without JS (Progressive Enhancement)<!-- .element: class="fragment" -->
- SEO purposes<!-- .element: class="fragment" -->
----

## When not render on the server?
----


- SEO is good enough already hint: [Mobile Friendly Test](https://search.google.com/test/mobile-friendly)<!-- .element: class="fragment" -->
- Small JS bundle<!-- .element: class="fragment" -->
- No budget for server ressources<!-- .element: class="fragment" -->
---

## Wrapping up
----
![Rendering comparison](https://developers.google.com/web/updates/images/2019/02/rendering-on-the-web/infographic.png)
---



