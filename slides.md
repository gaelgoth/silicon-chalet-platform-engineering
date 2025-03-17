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

<!--
- Equipe de 7 experts
- ~ 2 ans du Backstage
- || Azure Landing + Projet
- Example avec Azure
-->

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

<!--

- Introduction à la discipline du **Platform Engineering**
- Présentation du modèle adopté et des raisons de ce choix
- Transition vers les outils améliorant la **Developer Experience**
- Introduction à **Backstage**, suivi d’une démonstration de notre instance
- Conclusion et session de **Q&A**

-->

---
layout: top-title
color: red-light
class: text-center
---

:: title ::

# `Platform` vs `DevOps` vs `SRE`
<div class="text-sm opacity-80 mt-2">Understanding the distinct engineering roles</div>

:: content ::

 <!-- TODO: changer order 1) Platform 2) DevOps 3) SRE -->

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

<!--

- Il n'y pas qu'une seule definition chaque organisation a sa propre vision du DevOps

- **DevOps** est une **pratique** visant à rendre les équipes de développement **autonomes** sur l’ensemble du cycle de vie logiciel (*build, déploiement, exploitation*).
- **Rôles complémentaires** et interactions entre **DevOps, Platform Engineering et SRE**.
- **Platform Engineering** : mise en place d’outils internes avec un **focus sur l’expérience développeur**.
- **DevOps** : amélioration de la **vélocité des déploiements** et de l’**automatisation**.
- **SRE (Site Reliability Engineering)** : garantie de la **fiabilité, disponibilité et performance** des systèmes en production.

-  On va toujours retrouver ces roles complémentaires sur la platforme

-->

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

“discipline of designing and building toolchains and workflows that enable ==**self-service capabilities for software engineering**== organizations in the cloud native era” - [(platformengineering.org)](https://platformengineering.org/)
</SpeechBubble>

<SpeechBubble position="br" color='navy-light' shape="round" v-drag="[570,100,300,120]" >

“it allows companies to quickly develop
and deploy applications while ==**maintaining quality standards**==”
</SpeechBubble>

<SpeechBubble position="br" color='navy-light' shape="round" v-drag="[120,290,410,215]" >

“With DevOps, the market was more interested in shifting responsibility left and empowering individual developers to oversee the entire software life cycle. Now, as sprawl and shadow IT emerge, the pendulum seems to be shifting back toward a bit ==**more centralization and governance with platform engineering**==” - [(devops.com)](https://devops.com/whats-the-difference-between-devops-and-platform-engineering/#:~:text=Platform%20engineering%20is%20all%20about,processes%2C%20especially%20at%20large%20enterprises.)​
</SpeechBubble>


<SpeechBubble position="bl" color='zinc' shape="round" v-drag="[600,290,350,175]" >

"By 2026, 80% of software engineering organizations will establish ==**platform teams as internal providers of reusable services**==, components and tools for application delivery.“ - [(hashicorp.com)​](https://www.hashicorp.com/fr/on-demand/gartner-top-trends-for-2023-platform-engineering)
</SpeechBubble>

<!--
- KubeCon qui se déroule en ce moment, on a aussi la platformCon
- Existence de **groupes de travail** dédiés, à l’image de ceux autour de **Kubernetes**. -> platformengineering.org

- Les problèmes qu'on remarque:
  - Fragmentation des outils : La multiplication des outils et services
  - Manque conhérence:  où les équipes peuvent adopter des pratiques divergentes
  - Complexité croissante et évoltion rapide des technologies cloud-native (faut se tenir à jour)

- **Self-service** :
  - Ex: Commander un Account AWS, Licence GitHub Copilot, namespace k8s prêt à être utiliser
  - Déploiement rapide d’un environnement ou d’un outil en **quelques minutes**
  - On a le contrôle sur les paramètres et les prérequis des outils déployés
  - Le bon mantra:  **Zéro ticket** – tout doit être **automatisé** ! 😉

- Uniformiser les **outils et processus** pour réduire la complexité.
- **Avec une gouvernance centralisée** pour mieux structurer et standardiser.
- Mais aussi fournir des **solutions réutilisables et bien structurées**.
-->

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


<!--
Pourquoi le platform Platform Engineering ?

- 🌍 **Cloud-Native Complexity** → Les environnements modernes sont vastes et dynamiques. Comment suivre et améliorer cette situation?
- 🧠 **Réduire la charge cognitive** des développeurs → Les ingénieurs devraient se concentrer sur la construction, et non sur les frictions liés à l'infrastructure/outils
- **Garde de fou pour la sécurité et la gouvernance** → La sécurité doit être intégrée dès le départ, pas ajoutée après coup

🔹 Nos priorités
- ❌ Ce que nous évitons : **Forcer des architecture**s** applicatives rigides ou limiter l'autonomie des équipes des projet
- ✅ Ce que nous privilégions : Une expérience de développeur en **libre-service** avec des meilleures pratiques intégrées.
- 🚀 Mesure du succès : Temps de mise en production des nouveaux services - rapidité sans sacrifier la fiabilité et la qualité
-->

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

<!--
### **Projet vs. Plateforme : Avantages & Inconvénients**

#### **✅ Avantages d’un projet**
- **Flexibilité**
-  → Adaptation rapide aux besoins spécifiques.
-  → Ajout rapide de nouvelles fonctionnalités.
- **Liberté technologique** → Possibilité de changer facilement d’outils ou de technologies.

#### **❌ Inconvénients d’un projet**
- Disons que nous avons 7 ingénieurs DevOps
- Difficile à scale → Nécessite des ressources pour la configuration et la maintenance.
- **Manque de standardisation** →


#### **✅ Avantages d’une plateforme**
- **Évolution continue** → Adaptation aux besoins sans refonte majeure.
- **Mises à jour automatiques** → Sécurité et compatibilité assurées.
- **Préconfiguration avec d’autres services** → Simplification et gain de temps.

#### **❌ Inconvénients d’une plateforme**
- **Nécessité de faire les bons choix** → Une mauvaise architecture peut limiter l’efficacité.
- **Pas toujours adapté à tous les projets** → Certains cas nécessitent des approches plus flexibles.
- **Besoin d’une vision et d’une standardisation alignées** → Éviter l’incohérence et les dérives.

### **🔹 Exemple concret**
Un projet **.NET** fonctionnant avec **MSSQL** sur une **VM Windows**.
-->

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

<!--
- (Pas uniquement axée sur la solution technique)
- Traiter une plateforme comme un produit
- Focus sur les **besoins des utilisateurs** (Pas uniquement sur la solution technique)

- **Backlog commun** visible de tous
   - Prioriser les fonctionnalités en fonction des besoins
- **Feedback loop** entre les équipes pour une amélioration continue
- Lead Dev, Architecte qui vont porter l'initiative au projet


- Monitoring:
- **Projet responsable** de définir des alertes critiques (pourl le SRE)
- Aussi reponsable de mettre en place leur dashbaord de monitoring
- Support: Si les problèmes sont récurrents, les équipes OPS/SRE interviennent pour trouver des solutions

- Self-training (Important): Les équipes de développement sont formées pour utiliser la plateforme de manière autonome
- Steamline les bonnes pratiques de sécurité et de gouvernance

**Dev Portal**
- Self-service: Les équipes de développement peuvent créer et gérer leurs propres environnements
- Billing: Retour clair des coûts liés à l'utilisation de la plateforme; Aggrès le cout de Licence, storage, consomation de ressources
- Indicators: Tableau de bords pour suivre l'utilisation et les performances
- Accelerators pour aider les équipes à démarrer rapidement et suivant les bonnes pratiques

**Déploiement productifs**
- Déploiement de manière cloud native
-->

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

<!--
Objectif: statisfaire le client

**Project team**:
- Utilise la platform
- Responsable des données de leur application
- Responsable du cycle de vie de leur infra
- >You build it, you run it<
- Utilisation (si possible) et Contribution aux workload modules

**Workload modules**: Accelerators/blueprints qui permettent de créer des services rapidement et facilement
 - Streamline via des Golden samples, qui montre leur usage et comment les utiliser

**Landing Zone modules**: Assurer des services de bases pour le fonctionnement de la plateforme
 - Ex: IAM/RBAC, range IP VPC/VNET, Security, Logging, Monitoring
 - Resource partagées: Azure frontdoor (CDN, WAF, routing)

- **Support** (équipe dédiée pour cela): Gestion des tickets et escalation
- **Management**: Point de contacts pour la vente et les offres
-->

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

Améliorer l'expérience développeur:
- Apporter tout les informations centralisées pour amélioer les choix techniques
- Reduire le temps pour bootstrap des technologies
- Améliorer la collaboration avec une owernership des devs

- Use case: déployer un Jenkins ?
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
- Jenkins only ? Or Jenkins + Git + Auth Token (for Arti)
  - Assuré la sécurisation des tokens utilisés entre les outils
  - Automatiquement mettre le bon group pour l'accès aux ressources
-->

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

<!--

- Spotify fait face à une explosion de services : microservices, pipelines CI/CD, monitoring, alertes…
- Les développeurs passent plus de temps à naviguer dans cet écosystème qu’à écrire du code
- -> Nécessité d'un portail unique pour centraliser les outils et la documentation
- Ce projet interne est devenu Open source 2020 -> Rejoint CNCF en 2022
- Qui est devenu defactor le framework pour construire les IDPs

-->
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


<!--
- Enquête menée par DX en 2025 (qui eu même développe des IDP basé sur le projet open source Backstage)
- Leur enquête montre une domination de Backstage dans le marché des IDP
- Avant Backstage, nous avions aussi une solution développée en interne
-->


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

<!--

- **Catalog**: le point névralgique qui agit comme inventaire de tous les services et outils disponibles
  - API, Microservices, data pipelines, ML models, etc...
  - Ce catalog doit agire comme source de vérité qui permet de visualiser les dépendances entre les services
  - Modèle basé sur YAML : Chaque service est décrit par un fichier YAML contenant des métadonnée
  - Backend extensible pour intégrer des outils tiers (Cas facile Dans notre cas LDAP pour les utilisateurs et groupes)

- **TechDocs**: La doc en markdown
  - Utilise MkDocs sous le capot pour le rendu
  - Format markdown donc formalisé, versioné sur git, légé

- Software Templates:
  - Modèle au format pour effectuer du scaffolding
  - Encore work in progress mais surtout utilisé par les équipes qui souhaite automatiser l'initialisation de leur projet

- L'art de développer des plugins
  - Backstage est **extensible** via des plugins
  - intégrer des **outils tiers** ou créer des **fonctionnalités personnalisées**
  - ELCA: Gros besoins pour l'intégration avec l'ERP de l'entreprise durant la création des services
  - Risque: Si Backstage brille par sa flexibilité a un prix. "Chaque plugin personnalisé que nous développons devient une dette technique potentielle"

-->

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

<!--
- N'est pas comprise de base dans Backstage
- La sauce secrète pour orchestrer les tâches de la platforme
- Permet de gérer des tâches longues et asynchrone
- Permet de créer des workflows complexes et de les exécuter sur Kubernetes
es
- Tips: Workflow idempotent, donc pas de soucis si le workflow est relancé
- Alertantives: GitHub Actions, Jenkins, GitLab CI/CD
-->

---
layout: top-title
color: red-light
hideInToc: true
---

:: title ::

# <SimpleIconsBackstage /> Big picture

:: content ::

<img src="/images/elca-backstage-impl-big-picture.excalidraw.svg" alt="ELCA Backstage Big picture" class="m-auto" style="width: 78%;" />

<!--
- Dévelooppement custom:
- Middleware: Qui rajoute des fonctionalités pour les administrateurs et filtrage API (qui peux faire quel API calls)
- Gestion améliorées des logs
- Monitoring classique avec Prometheus et Grafana -> Remplacement prévu avec OTEL
- Argo Workflows: Orchestration des tâches de la plateforme
 -->

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

<!--

Défis

- Nous visons à centraliser et à améliorer la façon dont nous suivons et répondons aux incidents.

- L'équipe est responsable de la construction, du fonctionnement et du support de la plateforme.
- Nécessitant une large expertise dans de multiples domaines.

- Backstage n'est pas "plug and play" - il faut du temps et des efforts pour le maîtriser.
- En autre des skills full stacks en matière de développement web
Les équipes ont besoin de conseils et de soutien pour exploiter pleinement ses capacités.

-->



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

<!-- Source: Article Medium -->
