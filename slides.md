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
titlewidth: is-3
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

- <MdiBadgeAccountOutline /> `Gaël Gothuey`
- <MdiRocketLaunchOutline /> `DevOps Engineer` / `Platform Engineer` at ELCA
- <SimpleIconsBackstage /> `Backstage` Contributor
- <MdiServer /> `Homelab/Home` server enthusiast
- <DeviconPlainAzure /> `Azure` expert
- <MdiPhotoCamera /> Street photographer

---
layout: section
hideInToc: true
---

<div class="ml-30">

# What this presentation about ?

<hr>
<br>

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

# `Platform` vs `DevOps` vs `SRE`
<div class="text-sm opacity-80 mt-2">Understanding the distinct engineering roles</div>

:: content ::

<div className="grid grid-cols-3 gap-4 h-full items-center">
  <div className="bg-purple-50 border-2 border-purple-300 rounded-xl p-4 text-center h-full flex flex-col justify-center">
    <div className="mx-auto mb-3 text-purple-600">
      <CarbonCicsSystemGroup class="h-12 w-12" />
    </div>
    <h3 className="text-xl font-bold text-purple-800 mb-2">Platform Engineer</h3>
    <p className="text-sm text-gray-600 mb-3">Building tools for engineering teams</p>
    <div className="bg-purple-100 rounded-lg p-3 text-xs">
      <div className="mb-1"><strong>Focus:</strong> Internal Tooling, Infrastructure</div>
      <div className="mb-1"><strong>Clients:</strong> Developers, Engineering Teams</div>
      <div><strong>Example:</strong> Database setup from dev to prod</div>
    </div>
  </div>

<div className="bg-blue-50 border-2 border-blue-300 rounded-xl p-4 text-center h-full flex flex-col justify-center">
  <div className="mx-auto mb-3 text-blue-600">
    <CarbonIbmDevopsControl class="h-12 w-12" />
  </div>
  <h3 className="text-xl font-bold text-blue-800 mb-2">DevOps Engineer</h3>
  <p className="text-sm text-gray-600 mb-3">Improving deployment velocity</p>
  <div className="bg-blue-100 rounded-lg p-3 text-xs">
    <div className="mb-1"><strong>Focus:</strong> CI/CD Pipelines, Automation</div>
    <div className="mb-1"><strong>Clients:</strong> Developers and SREs</div>
    <div><strong>Example:</strong> User login dashboard monitoring</div>
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

---
layout: top-title
color: red-light
background: "#0f172a"
hideInToc: true
---

:: title ::

# `Platform Engineering` discipline
<div class="text-sm opacity-80 mt-2">Focused on the development of self-service toolchains, services, and processes</div>

:: content ::

<SpeechBubble position="bl" color='slate-light' shape="round" v-drag="[10,130,500,120]" >

"discipline of designing and building toolchains and workflows that enable ==**self-service capabilities for software engineering**== organizations in the cloud native era" - [(platformengineering.org)](https://platformengineering.org/)
</SpeechBubble>

<SpeechBubble position="br" color='navy-light' shape="round" v-drag="[570,100,300,120]" >

"it allows companies to quickly develop
and deploy applications while ==**maintaining quality standards**=="
</SpeechBubble>

<SpeechBubble position="br" color='navy-light' shape="round" v-drag="[120,290,410,215]" >

"With DevOps, the market was more interested in shifting responsibility left and empowering individual developers to oversee the entire software life cycle. Now, as sprawl and shadow IT emerge, the pendulum seems to be shifting back toward a bit ==**more centralization and governance with platform engineering**==" - [(devops.com)](https://devops.com/whats-the-difference-between-devops-and-platform-engineering/#:~:text=Platform%20engineering%20is%20all%20about,processes%2C%20especially%20at%20large%20enterprises.)​
</SpeechBubble>

<SpeechBubble position="bl" color='zinc' shape="round" v-drag="[600,290,350,175]" >

"By 2026, 80% of software engineering organizations will establish ==**platform teams as internal providers of reusable services**==, components and tools for application delivery." - [(hashicorp.com)​](https://www.hashicorp.com/fr/on-demand/gartner-top-trends-for-2023-platform-engineering)
</SpeechBubble>

---
layout: top-title
color: red-light
class: "text-left"
hideInToc: true
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
clicks: 1
hideInToc: true
---

:: title ::

# `Project` vs `Platform`
<div class="text-sm opacity-80 italic">What's the difference with a classical project? </div>

:: content ::

<div class=""><img src="/images/project-base-approach.excalidraw.svg" class="m-auto" style="width: 100%;"  /></div>

<div
  v-if="$slidev.nav.clicks === 1"
>
.Net <MdiDotNet/> <mdi-arrow-right /> Microsoft SQL Server <CarbonSql /> <mdi-arrow-right /> Windows Virtual Machine <MdiServer />

.Net <MdiDotNet/> <mdi-arrow-right /> PostgreSQL <SimpleIconsPostgresql /> <mdi-arrow-right /> Containers <CarbonWebServicesContainer/>
</div>

---
layout: top-title
color: red-light
hide: true
hideInToc: true
---

:: title ::

# `Project` vs `Platform`
<div class="text-sm opacity-80 italic">What's the difference with a classical project? </div>

:: content ::

<div class=""><img src="/images/price-model.excalidraw.svg" class="m-auto" style="width: 65%;"  /></div>

---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# `Platform` as product
<div class="text-sm opacity-80 italic">Building ecosystems that scale</div>

:: content ::

<img src="/images/platform-as-product.excalidraw.svg" alt="Platform as product" class="m-auto" style="width: 100%;" />

<v-switch>
  <template #1>
    <ArrowDraw color='red' v-drag="[720,80,100,50,150]" />
    <ArrowDraw color='red' v-drag="[720,102,100,700,215]" />
  </template>
  <template #2>
    <ArrowDraw color='red' v-drag="[375,50,100,50,90]" />
    <ArrowDraw color='red' v-drag="[375,103,100,790,270]" />
  </template>
  <template #3>
    <ArrowDraw color='red' v-drag="[110,50,100,50,90]" />
    <ArrowDraw color='red' v-drag="[110,104,100,790,270]" />
  </template>
</v-switch>

---
layout: top-title
color: red-light
preload: false
clicks: 1
hideInToc: true
---

:: title ::

# Teams organization
<div class="text-sm opacity-80 italic">Defined purpose and responsibilities</div>

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
class: "text-center"
---

# Developer Experience `DevEx`

<div class="text-gray-400">Empowering developers with the right tools</div>
<div class="">
  <toolsConstellation :numberOfTools="16" :rotationSpeed="0.7" />
</div>

<div class="absolute bottom-10 left-0 right-0 text-center text-sm opacity-70">
Developers have access to a comprehensive ecosystem of tools to enhance productivity
</div>

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

---
layout: side-title
color: red-light
transition: fade
side: left
titlewidth: is-4
align: rm-lt
title: <SimpleIconsBackstage /> `Backstage` Introduction
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

<img src="/images/elca-backstage-model.excalidraw.svg" alt="Platform Pillars" class="m-auto" style="width: 100%;" />

<v-switch>
  <template #1>
    <ArrowDraw color='red' v-drag="[690,80,100,50,150]"/>
  </template>
    <template #2>
    <ArrowDraw color='red' v-drag="[800,60,100,50,110]"/>
    <ArrowDraw color='red' v-drag="[675,340,100,50,320]"/>

  </template>
  <template #3>
    <ArrowDraw color='red' v-drag="[260,-30,100,270,40]"/>
    <ArrowDraw color='red' v-drag="[185,-30,100,260,148]"/>
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
- **Argo CD** is a GitOps deployment tool

</StickyNote>

---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# <SimpleIconsBackstage /> Big picture

:: content ::

<img src="/images/elca-backstage-impl-big-picture.excalidraw.svg" alt="ELCA Backstage Big picture" class="m-auto" style="width: 78%;" />

---
layout: intro
color: red-light
---

#  <SimpleIconsBackstage /> `Backstage` Demo

_Platform Engineering Demo_ <a href="https://backstage.svc.elca.ch/" class="ns-c-iconlink"><mdi-open-in-new /></a>

<br />

<MdiCheck /> Service Service <br />
<MdiCheck /> Cost Insights <br />
<MdiCheck /> Documentation <br />
<MdiCheck /> Golden samples <br />
<MdiCheck /> Catalog <br />
<MdiCheck /> Admin view <br />

---
layout: side-title
side: r
color: red-light
titlewidth: is-4
align: lm-lb
---

:: title ::
# Key Takeaways

# <mdi-arrow-left />

:: content ::

**🚧 Challenges**
- ==Enhancing isibility== into monitoring and alerting across the platform
- Facilitating access to ==short-lived sandbox== and test environments (e.g., AI/ML testing, POCs).
- ==Need skills==, the Platform Engineering Team handles everything (*Build*, *Run*, *Support*)
- ==Steep learning curve== for adopting Backstage

**🌟 Achievements**
- Backstage serves as the ==source of truth== for ==~3555 services==
- Achieved ==95% transition== from ==VMs to containers== for on-premises workloads
- ==90% of projects== have adopted CI/CD pipelines

---
layout: section
color: red-light
title: Q&A
---

# Thanks for listening! 👋

**Gaël Gothuey**

<br />

<p class="text-sm text-opacity-70">
  <mdi-email /> gael.gothuey@elca.ch <br>
  <mdi-linkedin /><a href="https://www.linkedin.com/in/gael-gothuey/" class="ns-c-iconlink">/gael-gothuey</a><br>
  <mdi-github /><a href="https://github.com/gaelgoth" class="ns-c-iconlink">/gaelgoth</a><br>
</p>

<br />

- [https://medium.com/elca-it](https://medium.com/elca-it/platform-engineering-building-a-portal-for-developers-with-backstage-c51e74662eba)
- https://platformengineering.org