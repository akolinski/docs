---
layout: post
title:  "Vue.js research"
date:   2019-09-23 09:00:00 +1000
categories: git
url: vue-js-research
---

<blockquote class="blockquote">
    We are going to cover topics such as SEO, SSR and much more to help solve questions when moving over to using Javascript Frameworks such as Vue, React or Angular.
</blockquote>

## Introduction

Some text.

### Search engine optimisation (SEO)

### Caching

#### Server side cache

Caching is a commonly used technique to improve the performance of any application, be it desktop, mobile or web. When dealing with web applications we can make good use of client-side caching using response headers that all browsers currently support. But, what if we have a complex and heavy page that takes 2 second to generate the HTML output?Even if we enable client-side cache for this page, the web server will still need to render the page for each different user accessing our web application. Think about the home page of a large news portal; do they process their HTML over and over again for each visitor?

This is where server-side cache comes in handy. The goal of server side cache is responding to the same content for the same request independently of the client’s request. In our example above, the first request that reaches our server would still take 2 seconds to generate the HTML, but the following requests would hit the cache instead and the server would be able to send the response in a few milliseconds.

There are many ways of doing it, it could be done with NGINX or a CDN like CloudFlare, but in this example we’ll see how to do it with Node.js and Express with minimal work and in a flexible way.

https://ssr.vuejs.org/guide/caching.html?fbclid=IwAR2wyfGusDSa5iXPdEtBeGX6S8u9yKT4xs5txbQeFeWKpqW6RmzEB3RBOXw#page-level-caching

https://ssr.vuejs.org/?fbclid=IwAR2zpbdskSPC-01RSMt109GpKo5QkNFpeyRCbXWrbn3_BLoHWTRZTSCeBS8#what-is-server-side-rendering-ssr

READ ABOUT CLOUDFRONT

### jQuery or Vue

Did you know that you can incorporate Vue into your project the same way that you would incorporate jQuery. In this <a href='https://www.smashingmagazine.com/2018/02/jquery-vue-javascript/' target='_blank'>article</a> they provide examples for capturing user inputs, storing user inputs, toggling classes, hiding and showing and submitting forms.

It is definitely ok to use jQuery if it suits you! Vue is also a pretty nice abstraction for small sites that don’t need a lot of overhead. Vue is comparable in size, easy to reason about, and it’s fairly trivial to switch small pieces of functionality to Vue without rewriting your HTML in JavaScript.

Due to Vue’s flexibility, it’s also easy to transition this code to a build step and component structures if you’d like to adopt a more complex structure over time. The nice thing about the flexibility to choose either way of incorporating Vue into your project means that you’re not pressed to change your style of working all at once, and you can even make changes slowly over time. This is why people call Vue the progressive framework.

### Bootstrap 5

Bootstrap is removing jQuery as a dependency when using the framework. Moving over to using Vue.js and pure javascript is the move the industry is leaning towards.

### ExpressionEngine

Having a thin PHP layer to still use what we have in place.

#### References

<a href="https://www.smashingmagazine.com/2019/05/vue-js-seo-reactive-websites-search-engines-bots/" target="blank">Vue.js And SEO: How To Optimize Reactive Websites For Search Engines And Bots</a><br>
<a href="https://www.smashingmagazine.com/2018/02/jquery-vue-javascript/" target="blank">Replacing jQuery With Vue.js: No Build Step Necessary</a><br>
<a href="https://medium.com/the-node-js-collection/simple-server-side-cache-for-express-js-with-node-js-45ff296ca0f0" target="blank">Simple server side cache for Express.js with Node.js</a><br>
