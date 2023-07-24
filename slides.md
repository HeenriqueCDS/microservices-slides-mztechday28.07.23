---
theme: seriph
background: images/cover.jpeg
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Microservices Lightning Talk
  lecture by Henrique de Carvalho

drawings:
  persist: false
transition: slide-left
title: Microservices - The future of Software Architecture?
---

# Microservices - The future of Software Architecture?

The fractioned applications paradigm

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
layout: image-right
image: images/charming-speaker.jpeg
---

# About the speaker

José **Henrique** Carvalho dos Santos is a Software Engineer specialized in React.js and Node.js and passionate about **Software Architecture**

- 👶 **Started early** - Writing code since 12 years old
- 🛠️ **Technologies** - Typescript, React.js, Node.js, RabbitMQ, Docker, Git, PostgreSQL, MongoDB, Python, GoLang, LuaScript, Java, C#, GCP, AWS
- 🕹️ **Gamer** - A very competitive player


<br>
<br>

More about [me](https://henrique-dev.vercel.app/)!

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
layout: default
---

# Table of contents


<Toc></Toc>

---
transition: slide-up
---

# What is microservices?

Microservices is a style of software development architecture that, as the name implies, is based on services and/or smaller applications, which make up a larger system, simple isn't it? this style of architecture aims to streamline development, facilitate scalability and introduce new features in this rapidly growing technology market

### How to implement it?

To talk first about how to implement this designed style, it should be clear that there is no fully defined standard of rules or something like "the 10 commands of microservices", but there are some standards that are perpetuated following applications that follow this style , here we are going to mention some of them, but first an example of a microservices ecosystem

---

# Example

<div class="w-full h-100 flex flex-col items-center gap-4" v-click-hide>
  <h3>E-commerce monolith application</h3>
  <div class="w-full h-100 border rounded-3xl flex justify-around items-center">
    <div class="w-187.5px h-187.5px border border-blue rounded-full flex items-center justify-center">Cart Module</div>
    <div class="w-187.5px h-187.5px border border-blue rounded-full flex items-center justify-center">Payment Module</div>
    <div class="w-187.5px h-187.5px border border-blue rounded-full flex items-center justify-center">Invoice Module</div>
    <div class="w-187.5px h-187.5px border border-yellow  flex items-center justify-center">Database</div>
  </div>
</div>
<div v-click="1" class="w-full h-100 flex flex-col items-center gap-4">
  <h3>E-commerce distributed microservices</h3>
    <div class="w-full h-100 flex justify-asrcround items-center">
      <div class="w-250px h-250px border border-white rounded-3xl flex items-center justify-center relative ">
        Cart Service
        <div class="w-80px h-70px border border-yellow  flex items-center justify-center absolute bottom-16px right-16px text-xs">Database</div>
      </div>
      <div class="w-250px h-250px border border-white rounded-3xl flex items-center justify-center relative ">
        Payment Service
        <div class="w-80px h-70px border border-yellow  flex items-center justify-center absolute bottom-16px right-16px text-xs">Database</div>
      </div>
      <div class="w-250px h-250px border border-white rounded-3xl flex items-center justify-center relative ">
        Invoice Service
        <div class="w-80px h-70px border border-yellow  flex items-center justify-center absolute bottom-16px right-16px text-xs">Database</div>
      </div>
    </div>
    <audio controls autoplay>
      <source src="sounds/among-us-role-reveal-sound.mp3" type="audio/mpeg">
    </audio>
</div>

<style>
  .slidev-vclick-hidden {
  display: none
}
</style>

---

# Microservices Vs Monoliths

<div grid="~ cols-2 gap-2" m="-t-2">
<p>
In the architecture of a monolith, all our processes are centralized in a single service, which brings a cost, if I need to scale again, for example, going back to e-commerce, my cart system, I will have to re-upload my entire application, in addition to the fact that, in a poorly architected monolith, it is possible that I end up breaking parts that work together with my cart, such as my shopping functionality, also having my code growing and becoming bigger and more complex with each maintenance, which makes it difficult to implement new functionalities and limits the implementation of new ideas
</p>
<p>
In the microservices architecture, we have our softwares fragmented, they communicate through well-defined API interfaces, each one of them has a specific functionality and brings us more decoupled processes, bringing greater scalability to our project, where changing one service should not affect the functioning of the other
</p>

</div>



---
layout: image-right
image: https://www.wissenschaft.de/wp-content/uploads/i/S/iStock-1340728386-990x679.jpg
---

# Characteristics

- 🦾 **Autonomous** - These little fragments of software of ours, they must be able to function without depending on any or all other services and they must also be able to scale without affecting any other services, they must communicate with each other in a solid and well defined way through your communication protocol (HTTP, Message Broker, WebSockets...)
- 🛠️ **Specialized** - Each microservice must have a unique specialty, a problem to solve, as we mentioned earlier in our e-commerce example, if the complexity of this microservice increases, it can be divided into more fragments to facilitate maintenance

<style>
  li {
    font-size: 16px;
  }
</style>

---

# Let's put it all on the table


<div grid="~ cols-2 gap-2" m="-t-2">
  <div>
    <h3>Where is better?</h3>
    <ul>
      <li>Decentralized Governance</li>
      <li>Polyglot persistance</li>
      <li>Resilience</li>
    </ul>
  </div>
    <div>
    <h3>Where is worse?</h3>
    <ul>
      <li>Design for failure</li>
      <li>Authenticating, Logging, Communicating...</li>
      <li>Debugging</li>
    </ul>
  </div>
</div>

---
layout: image-right
image: https://www.incimages.com/uploaded_files/image/1920x1080/getty_494605768_2000133320009280151_316966.jpg
---

# Taking better architecture decisions

- 🛠️ **How we are improving architecure decisions in Squad Tools** - We've been improving a lot in or architectural decisions, talking about microservices, we have two interesting cases that can be spoken of here
- ➗ **Splitting a microservice** - One of our microservices have grown, his main goal used to be importing our customers spreadsheets with some quotas data in our platform, but them it was possible to import from an external provider, which was problematic having them both in the same application due simultaneous imports
- 🦾 **Do not making they dependent on each other** - Another case it was when we faced a change with the authentication from an external api we are consuming, in the old method both application were using the same token, now they have their on token, which does not interfere on each others functionality

<style>
  li {
    font-size: 12px;
  }
  
</style>
