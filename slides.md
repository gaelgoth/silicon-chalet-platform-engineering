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

 <!-- TODO: changer order 1) Platform 2) DevOps 3) SRE -->

<div class="grid grid-cols-3 gap-4 h-full items-center">
  <div class="bg-purple-50 border-2 border-purple-300 rounded-xl p-4 text-center h-full flex flex-col justify-center">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-12 w-12 mx-auto text-purple-600 mb-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01" />
    </svg>
    <h3 class="text-xl font-bold text-purple-800 mb-2">Platform Engineering</h3>
    <p class="text-sm text-gray-600 mb-3">Building tools for engineering teams</p>
    <div class="bg-purple-100 rounded-lg p-3 text-xs">
      <div class="mb-1"><strong>Focus:</strong> Internal Tooling, Infrastructure</div>
      <div class="mb-1"><strong>Clients:</strong> Developers, Engineering Teams</div>
      <div><strong>Example:</strong> Database setup from dev to prod</div>
    </div>
  </div>

  <div class="bg-blue-50 border-2 border-blue-300 rounded-xl p-4 text-center h-full flex flex-col justify-center">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-12 w-12 mx-auto text-blue-600 mb-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
    </svg>
    <h3 class="text-xl font-bold text-blue-800 mb-2">DevOps</h3>
    <p class="text-sm text-gray-600 mb-3">Improving deployment velocity</p>
    <div class="bg-blue-100 rounded-lg p-3 text-xs">
      <div class="mb-1"><strong>Focus:</strong> CI/CD Pipelines, Automation</div>
      <div class="mb-1"><strong>Clients:</strong> Developers and SREs</div>
      <div><strong>Example:</strong> User login monitoring</div>
    </div>
  </div>

  <div class="bg-green-50 border-2 border-green-300 rounded-xl p-4 text-center h-full flex flex-col justify-center">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-12 w-12 mx-auto text-green-600 mb-3" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
    </svg>
    <h3 class="text-xl font-bold text-green-800 mb-2">SRE</h3>
    <p class="text-sm text-gray-600 mb-3">Hosting reliable production products</p>
    <div class="bg-green-100 rounded-lg p-3 text-xs">
      <div class="mb-1"><strong>Focus:</strong> Reliability, On-call Support</div>
      <div class="mb-1"><strong>Clients:</strong> Business Stakeholders</div>
      <div><strong>Example:</strong> 99.9% database uptime</div>
    </div>
  </div>
</div>

<!--
- Devops est une pratique
- Rendre autonome une équipe dev to prod (build, deployment
- Role complémentaire et interractions
-->

---
layout: top-title
color: red-light
background: '#0f172a'
---

:: title ::

# `Platform Engineering`  discipline
<div class="text-sm opacity-80 mt-2">Focused on the development of self-service toolchains, services, and processes</div>

:: content ::

<SpeechBubble position="bl" color='slate-light' shape="round" v-drag="[10,130,500,120]" >

“discipline of designing and building toolchains and workflows that enable **self-service capabilities for software engineering** organizations in the cloud native era” - [(ref)](https://platformengineering.org/)
</SpeechBubble>

<SpeechBubble position="br" color='navy-light' shape="round" v-drag="[570,100,300,120]" >

“it allows companies to quickly develop
and deploy applications while **maintaining quality standards**”
</SpeechBubble>

<SpeechBubble position="br" color='slate' shape="round" v-drag="[120,290,410,215]" >

“With DevOps, the market was more interested in shifting responsibility left and empowering individual developers to oversee the entire software life cycle. Now, as sprawl and shadow IT emerge, the pendulum seems to be shifting back toward a bit **more centralization and governance with platform engineering**” - [(ref)](https://devops.com/whats-the-difference-between-devops-and-platform-engineering/#:~:text=Platform%20engineering%20is%20all%20about,processes%2C%20especially%20at%20large%20enterprises.)​
</SpeechBubble>


<SpeechBubble position="bl" color='zinc' shape="round" v-drag="[620,290,310,175]" >

"By 2026, 80% of software engineering organizations will establish **platform teams as internal providers of reusable services**, components and tools for application delivery.“ - [(ref)​](https://www.hashicorp.com/fr/on-demand/gartner-top-trends-for-2023-platform-engineering)
</SpeechBubble>

<!-- - Just ce qui est en gras
- Self-servicing capabilities
- Script and aumontation for deployment and management
- Quality standards, to achieve good and also define standard (vs devops where give flexibility to project without good standard)
- So at the end, we have a governance in place
 -->

---
layout: top-title
color: red-light
---

:: title ::

# `Project` vs `Platform`
<div class="text-sm opacity-80 italic">What's the difference with a classical project? </div>

:: content ::

<div class=""><img src="/images/project-base-approach.excalidraw.svg" class="m-auto" style="width: 100%;"  /></div>

<!-- - Example with a .Net project, running mssql on a Windows VM
- TODO: Add graph price-model

project (Pro):

- Flexibility
- New feature can be quickly added
- Can switch to another technology

project (Cons):

- Needs hands to scale, configure and update
- Lack of standardization


Platform (Pro):

- Scale
- Auto-updated
- Pre-configured with other services

Platform (Cons):

- Crucial to make right choices
- Not the best choice for all projects
- Needs standard and aligned vision

-->


---
layout: top-title
color: red-light
hide: true
---

:: title ::

# `Project` vs `Platform`
<div class="text-sm opacity-80 italic">What's the difference with a classical project? </div>

:: content ::

<div class=""><img src="/images/price-model.excalidraw.svg" class="m-auto" style="width: 65%;"  /></div>


---
layout: top-title
color: red-light
class: "text-left"
---

:: title ::

# `Platform Engineering` objectives
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
      <p><strong>Keep</strong> project creativity and accountability: Dictating specific application architecture or hindering team autonomy</p>
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
---

:: title ::

# `Platform` as product

:: content ::

<img src="/images/platform-as-product.excalidraw.svg" alt="Platform as product" class="m-auto" style="width: 100%;" />

<v-switch>
  <template #1>
    <ArrowDraw color='red' v-drag="[720,80,100,50,150]"/>
    <ArrowDraw color='red' v-drag="[720,80,100,700,215]"/>
  </template>
  <template #2>
    <ArrowDraw color='red' v-drag="[410,50,100,50,90]"/>
    <ArrowDraw color='red' v-drag="[410,80,100,790,270]"/>
  </template>
  <template #3>
    <ArrowDraw color='red' v-drag="[170,50,100,50,90]"/>
    <ArrowDraw color='red' v-drag="[170,80,100,790,270]"/>
  </template>
</v-switch>

<!-- - Project defines alerts (the important one) but they still implement a full dashboard of their projet
- OPS/SRE team is responsible to make that the service is running (But a part it's in the hand of the hyperscale such as Azure)
- If there is reccurent issue, the OPS/SRE came to find a solution/monitoring -->



---
layout: top-title
color: red-light
preload: false
clicks: 1
---

:: title ::

# Teams Organization


:: content ::

<div class="relative">
  <img src="/images/platform-team-organization.excalidraw.svg" alt="Platform as product" class="absolute top-0 left-0 m-auto" style="width: 75%;" />
      <div
        v-if="$slidev.nav.clicks === 1"
        class="absolute top-0 left-0 m-auto"
        style="width: 75%;"
      >
        <img
          src="/images/platform-team-organization-2.excalidraw.svg"
          alt="Platform as product update"
          class="w-full"
        />
      </div>
</div>



---
layout: full
color: red-light
class: 'text-center'
---

# Developer Experience `DevEx`

<div class="text-gray-400">Empowering developers with the right tools</div>
<div class="">
  <toolsConstellation :numberOfTools="16" :rotationSpeed="0.7" />
</div>

<div class="absolute bottom-10 left-0 right-0 text-center text-sm opacity-70">
Developers have access to a comprehensive ecosystem of tools to enhance productivity
</div>

<!--
Good to have tools but complicated to streamline all of them
- Jenkins only ? Or Jenkins + Git + Token (for Arti)
  - Ensure security between tools


Improve Developer Experience by providing :
- All information possible to improve code.
- All information to make better technical choices.
- Reduce time to bootstrap technologies.
Implement DevOps – Developer ownership
-->


---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# Developer Experience `DevEx`
<div class="text-sm opacity-80 italic">Where tools work better together</div>

:: content ::

<div class=""><img src="/images/provisioning-wizard.png" class="m-auto" style="width: 100%;"  /></div>


<!--
Good to have tools but complicated to streamline all of them
- Jenkins only ? Or Jenkins + Git + Token (for Arti)
  - Ensure security between tools


Improve Developer Experience by providing :
- All information possible to improve code.
- All information to make better technical choices.
- Reduce time to bootstrap technologies.
Implement DevOps – Developer ownership
-->

---
layout: side-title
color: red-light
transition: fade
side: left
titlewidth: is-4
align: rm-lt
title: Backstage Introduction
---


:: title ::

# <SimpleIconsBackstage /> Backstage

One hub for developer information and tools

<div class="text-sm left-0 w-full fw-200">

  \* `IDP: Internal Developer Platform`
</div>


:: content ::

## <SimpleIconsBackstage /> Timeline:

-  **Developed at Spotify <MdiSpotify />** to centralize developer tools and documentation
-  **Open-sourced in 2020** to benefit the broader community
-  **Joined CNCF <SimpleIconsCncf /> Incubator in 2022**, growing as an industry standard

## <SimpleIconsTarget /> Community:

- **60+ open-source plugins** in the Plugin Marketplace
- **100** publicly listed [adopters](https://github.com/backstage/backstage/blob/master/ADOPTERS.md)
- **15k+ stars** on GitHub <MdiGithub />



---
layout: side-title
color: red-light
side: left
titlewidth: is-4
align: rm-lt
title: Backstage Introduction
hideInToc: true
---


:: title ::

# <SimpleIconsBackstage /> Backstage

One hub for developer information and tools

<div class="text-sm left-0 w-full fw-200">

  \* `IDP: Internal Developer Platform`
</div>


:: content ::

## <MdiGraphLine /> The IDP state

DX surveyed 180 companies to understand how they were approaching internal developer portals (IDPs), their result:

<br/>
<img src="/images/dx-survey.png" alt="Dx Survey" class="m-auto" style="width: 100%;" />

<div class="fw-200 text-sm" >

\* Published on Mar 19, 2025 - Ref: https://newsletter.getdx.com/p/backstage-and-the-developer-portal-market
</div>




---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# <SimpleIconsBackstage /> and ELCA

<div class="text-sm opacity-80 italic">Our Backstage model</div>

:: content ::

<img src="/images/elca-backstage-model.webp" alt="Platform Pillars" class="m-auto" style="width: 90%;" />

<v-switch>
  <template #1>
    <ArrowDraw color='red' v-drag="[670,120,100,50,150]"/>
  </template>
  <template #2>
    <ArrowDraw color='red' v-drag="[800,110,100,50,110]"/>
  </template>
  <template #3>
    <ArrowDraw color='red' v-drag="[320,5,100,270,40]"/>
    <ArrowDraw color='red' v-drag="[250,10,100,260,140]"/>
  </template>
</v-switch>

---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# Self-Servicing

<div class="text-sm opacity-80 italic">Async Processes – The Agnostic Solution</div>

:: content ::

## <SimpleIconsArgo /> Argo Workflows:

- **Kubernetes-native** workflow engine
- **Handles long-running tasks**
- **Schedules jobs** (state imports, health checks, cleanup)
- **Runs any container-based language** (Python <MdiLanguagePython />, Open Tofu <SimpleIconsOpentofu />, bash <SimpleIconsGnubash />, Powershell <MdiPowershell />)
- **Web UI for visualization**

<StickyNote color="red-light" textAlign="left" width="220px" v-drag="[750,30,190,180,8]">

**Not to be confused with Argo CD**

- **Argo Workflows** automates workflows in Kubernetes
- **Argo CD** is a GitOps deployment tool.

</StickyNote>


---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# <SimpleIconsBackstage /> Big picture

<div class="text-sm opacity-80 italic">Mastering customization: Build your own plugins</div>

:: content ::

  <img src="/images/elca-backstage-impl-big-picture.excalidraw.svg" alt="ELCA Backstage Big picture" class="m-auto" style="width: 78%;" />


---
layout: intro
color: red-light
---

#  <SimpleIconsBackstage /> Backstage Demo


_Platform Engineering Demo_ <a href="https://backstage.svc.elca.ch/" class="ns-c-iconlink"><mdi-open-in-new /></a>


<br />

<MdiCheck /> Service Service <br />
<MdiCheck /> Cost Insights <br />
<MdiCheck /> Documentation <br />
<MdiCheck /> Golden samples <br />
<MdiCheck /> Catalog <br />
<MdiCheck /> Admin view <br />

---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# Pillars

<div class="text-sm opacity-80 italic">Still developing our pillars</div>

:: content ::

<img src="/images/platform-pillars.excalidraw.svg" alt="Platform Pillars" class="m-auto" style="width: 100%;" />

<div class="absolute bottom-20 left-0 right-0 text-center text-sm opacity-70">
Continuing to provide a great experience by having that single pane of glass
</div>

<!--

- Rajouter (au dessus) des pilliers une direction
-

 -->



