# Meetup at 42 Lausanne — Platform Engineering

This is the Slidev deck used for the Silicon Chalet meetup talk on Platform Engineering.
📅 [Event link](https://www.meetup.com/silicon-chalet/events/306722286/?eventOrigin=group_upcoming_events)

- 🌐 **Web view**: [gaelgoth.github.io/silicon-chalet-platform-engineering](https://gaelgoth.github.io/silicon-chalet-platform-engineering)
- 📄 **PDF**: [Download slides (PDF)](/slides.pdf)


## Usage

- Set nodejs version `nvm use`
- install pnpm if you haven't yet `npm install -g pnpm`
- Install the dependencies with `pnpm install`
- Start the development server with `pnpm dev`

To export to pdf:

`pnpm export`

## Publishing live

To auto publish live enable github pages from github actions on your forked repo.


## Custom animations

`toolsConstellation.vue`

```html
<div class="flex justify-center items-center w-full h-full">
  <toolsConstellation :numberOfTools="16" :rotationSpeed="0.7" />
</div>
```



## Sources

**Icons**: https://iconify.design/

**Theme**: https://github.com/gureckis/slidev-theme-neversink