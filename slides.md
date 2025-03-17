---
colorSchema: light
color: red-light
routerMode: hash
layout: cover
theme: neversink
neversink_slug: Platform Engineering - ELCA
transition: slide-left
hideInToc: true
---

# Platform Engineering
*Building a portal for Developers with Backstage*

**Gaël Gothuey**
<Email v="gael.gothuey@elca.ch" color="red" />

---
layout: side-title
side: l
color: rose-light
titlewidth: is-6
align: rm-lm
title: whoami
hideInToc: true
---

:: title ::

# `$ whoami`

<p class="text-sm text-opacity-70">
  <mdi-github /> gaelgoth<br>
  <mdi-web /> gothuey.dev
</p>

:: content ::

- `Gaël Gothuey`
- `DevOps Engineer` / `Platform Engineer` at ELCA
- `Backstage` Contributor
- `Homelab/Home` server enthusiast
- Street photographer

---
layout: section
hideInToc: true
---

<div class="ml-30">

# What this presentation about ?

<hr>
<br>

<!-- <span class='text-amber-300'>
 -->
 <span>
<Toc />
</span>

</div>

---
layout: top-title
color: red-light
class: text-center
---

:: title ::

# `DevOps` vs `SRE` vs `Platform`
<div class="text-sm opacity-80 mt-2">Understanding the distinct engineering roles</div>

:: content ::

<div class="grid grid-cols-3 gap-4 mt-4">
  <div class="bg-blue-500 bg-opacity-20 p-4 rounded-lg border-2 border-blue-500 shadow-md">
    <div class="flex justify-center mb-2">
      <mdi:rocket-launch inline class="text-4xl text-blue-500" />
    </div>
    <h3 class="font-bold text-xl mb-2 text-blue-500">DevOps</h3>
    <p>Improving deployment velocity of the product</p>
    <div class="mt-4 text-sm">
      <strong>Primary Focus:</strong> CI/CD Pipelines, Automation<br>
      <strong>Clients:</strong> Developers and SREs
    </div>
  </div>

  <div class="bg-green-500 bg-opacity-20 p-4 rounded-lg border-2 border-green-500 shadow-md">
    <div class="flex justify-center mb-2">
      <mdi:shield-check inline class="text-4xl text-green-500" />
    </div>
    <h3 class="font-bold text-xl mb-2 text-green-500">SRE</h3>
    <p>Hosting a reliable product in Production</p>
    <div class="mt-4 text-sm">
      <strong>Primary Focus:</strong> Reliability, On-call Support<br>
      <strong>Clients:</strong> Business Stakeholders
    </div>
  </div>

  <div class="bg-purple-500 bg-opacity-20 p-4 rounded-lg border-2 border-purple-500 shadow-md">
    <div class="flex justify-center mb-2">
      <mdi:tools inline class="text-4xl text-purple-500" />
    </div>
    <h3 class="font-bold text-xl mb-2 text-purple-500">Platform</h3>
    <p>Building tools for other engineering teams</p>
    <div class="mt-4 text-sm">
      <strong>Primary Focus:</strong> Internal Tooling, Infrastructure<br>
      <strong>Clients:</strong> Developers, Engineering Teams
    </div>
  </div>
</div>

---
layout: top-title
color: red-light
background: '#0f172a'
---

:: title ::

# `Platform` discipline
<div class="text-sm opacity-80 mt-2">Focused on the development of self-service toolchains, services, and processes</div>

:: content ::

<SpeechBubble position="bl" color='slate-light' shape="round" v-drag="[10,130,500,120]" >

“discipline of designing and building toolchains and workflows that enable **self-service capabilities for software engineering** organizations in the cloud native era” - [(ref)](https://platformengineering.org/)
</SpeechBubble>

<SpeechBubble position="bl" color='navy-light' shape="round" v-drag="[570,100,300,120]" >

“it allows companies to quickly develop
and deploy applications while **maintaining quality standards**”
</SpeechBubble>


<SpeechBubble position="bl" color='slate' shape="round" v-drag="[120,290,410,215]" >

“With DevOps, the market was more interested in shifting responsibility left and empowering individual developers to oversee the entire software life cycle. Now, as sprawl and shadow IT emerge, the pendulum seems to be shifting back toward a bit **more centralization and governance with platform engineering**” - [(ref)](https://devops.com/whats-the-difference-between-devops-and-platform-engineering/#:~:text=Platform%20engineering%20is%20all%20about,processes%2C%20especially%20at%20large%20enterprises.)​
</SpeechBubble>


<SpeechBubble position="bl" color='zinc' shape="round" v-drag="[620,290,310,175]" >

"By 2026, 80% of software engineering organizations will establish **platform teams as internal providers of reusable services**, components and tools for application delivery.“ - [(ref)​](https://www.hashicorp.com/fr/on-demand/gartner-top-trends-for-2023-platform-engineering)
</SpeechBubble>

---
layout: top-title
color: red-light
background: "#0f172a"
---

:: title ::

# `Project` vs `Platform`
<div class="text-sm opacity-80 italic">What's the difference with a classical project? </div>

:: content ::

<div class=""><img src="/images/project-base-approach.excalidraw.svg" /></div>

---
layout: top-title
color: red-light
class: "text-left"
---

:: title ::

# `Platform` objectives
<div class="text-sm opacity-80 italic">Enabling developer autonomy in complex systems</div>

:: content ::

<div class="grid grid-cols-2 gap-8">

<div>
  <h3 class="font-bold mb-4"><mdi:arrow-decision-outline class="inline" />
    Why Platform Engineering?
  </h3>

  <div class="bg-opacity-30 p-4 rounded-lg border-l-4 border-amber-500" >
    <ul class="space-y-2 list-none pl-0">
      <li class="flex items-center"><mdi:trending-up class="text-3xl mr-2 text-amber-400" /> Increasing complexity of cloud-native environments</li>
      <li class="flex items-center"><mdi:account-group class="text-2xl mr-2 text-amber-400" /> Developer cognitive load reduction</li>
      <li class="flex items-center"><mdi:refresh class="text-2xl mr-2 text-amber-400" /> Accelerating development cycles</li>
      <li class="flex items-center"><mdi:security class="text-2xl mr-2 text-amber-400" /> Consistent governance and security</li>
    </ul>
  </div>
</div>

<div>
  <h3 class="text-xl font-bold mb-4"><mdi:target class="inline" /> Our Priorities</h3>

  <div class="bg-opacity-20 p-4 rounded-lg border-l-4 border-red-500 mb-4">
    <div class="flex items-center">
      <mdi:close-circle class="text-3xl text-red-400 mr-2" />
      <p><strong>Not</strong> our responsibility: Dictating specific application architecture or hindering team autonomy</p>
    </div>
  </div>

  <div class="bg-opacity-20 p-4 rounded-lg border-l-4 border-green-500 mb-4">
    <div class="flex items-center">
      <mdi:check-circle class="text-4xl text-green-400 mr-2" />
      <p><strong>Top</strong> priority: Self-service developer experience with guardrails</p>
    </div>
  </div>

  <div class="bg-opacity-20 p-4 rounded-lg border-l-4 border-blue-500">
    <div class="flex items-center">
      <mdi:speedometer class="text-4xl text-blue-400 mr-2" />
      <p><strong>Key</strong> metric: Time to production for new services</p>
    </div>
  </div>
</div>

</div>

---
layout: top-title
color: red-light
background: "#0f172a"
---

:: title ::

# `Platform` as product

:: content ::

<img src="/images/platform-as-product.excalidraw.svg" alt="DevEx Meme" class="m-auto" style="width: 100%;" />


<v-switch>
  <template #1>
    <ArrowDraw color='red' v-drag="[720,80,100,50,150]"/>
    <ArrowDraw color='red' v-drag="[720,80,100,790,215]"/>
  </template>
  <template #2>
    <ArrowDraw color='red' v-drag="[500,80,100,50,90]"/>
    <ArrowDraw color='red' v-drag="[500,80,100,700,270]"/>
  </template>
  <template #3>
    <ArrowDraw color='red' v-drag="[150,120,100,700,330]"/>
    <ArrowDraw color='red' v-drag="[90,100,100,700,250]"/>
  </template>
</v-switch>


---
layout: center
class: 'text-center'
title: DevEx meme
hideInToc: true
---

<img src="/images/devex-meme.webp" alt="DevEx Meme" class="m-auto" style="width: 50%;" />

---
layout: center
class: 'text-center'
background: '#0f172a'
---

# Developer Experience `DevEx`

<div class="text-gray-400 mb-10">Empowering developers with the right tools</div>
<div class="flex justify-center items-center w-full h-full">
  <toolsConstellation :numberOfTools="16" :rotationSpeed="0.7" />
</div>



<div class="absolute bottom-10 left-0 right-0 text-center text-sm opacity-70">
Developers have access to a comprehensive ecosystem of tools to enhance productivity
</div>

<!--
Improve Developer Experience by providing :
- All information possible to improve code.
- All information to make better technical choices.
- Reduce time to bootstrap technologies.
Implement DevOps – Developer ownership
-->
