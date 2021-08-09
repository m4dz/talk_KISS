---
title: KISS Your UI
theme: ../divRIOTS_slidev-theme
permalink: https://talks.m4dz.net/kiss-your-ui/
author: m4dz
twitter: m4d_z
---

Design Systems, the Developer Way

---

<Giphy id="FspLvJQlQACXu" caption="Here's a Story of Interfaces" class="h-4/5" />

---
layout: media
---

# It always starts well...

<Figure src="./img/ui-elements.png" class="h-4/5"/>

---
layout: media
---

# ... but often ends in tears

<Figure src="./img/pnc-buttons.jpg" class="h-4/5"/>

---
layout: punch
---

User eXperience <br />
requires <mark>consistency</mark>

---
layout: punch
class: sm
---

How could we **maintain** <br />
a high level of **abstraction** <br />
to avoid code nightmares?

---
layout: media
---

# We need a global view

<Figure src="./img/codemund-wireframe.png" />

---
layout: leaf
---

# From UI to Atoms

---
layout: media
---

<Giphy id="SLUKIZdUcpujS" caption="Let's talk about components " />

---

# We all use components

<v-clicks>

- *Designer* <br/>
  produce wireframes, moodboards, concepts, using… components
- *Front-end Designer* <br />
  build interfaces with semantics and CSS frameworks that are… components-oriented
- *Front-end Developer* <br />
  use separation of concerns patterns supported by… components frameworks

</v-clicks>

---
layout: punch
---

We even made a <br>
**standard** named <br>
<mark>WebComponent</mark>!

---

# There's a lot of Developers Tools

- Hybrid
- LitElement
- Polymer
- Slim.js
- Stencil
- *etc*.

---
layout: media
---

# Defined by **Brad Frost** with Atomic Design

<Figure src="./img/atomic-design.png" caption="10 years ago" class="w-4/5"/>

---
layout: quote
class: sm
---

> Atomic Design details all that goes into creating and maintaining robust design systems, allowing your organization to roll out higher quality, more consistent UIs faster than ever before.

---

## Atoms

- Smallest available structure
- Tokens structure
- *e.g.* typography settings, colors...

---

## Molecules

- Based-on **Atoms**
- Essential units
- Expose **props**
- *e.g.* button, form field, hero...

---

## Organisms

- Built from **Molecules**
- UI separation of concerns
- *e.g.* form, nav, card, footer...

---

## Templates

- UI advanced wireframe
- Agregates **Organisms** and **Molecules**
- Act like a **Blueprint**
- **Pages** are Templates instances

---
layout: leaf
---

# Make it all come together

---
layout: punch
---

From a Designer PoV <br />
they're <mark>Design Systems</mark>

---
layout: quote
class: sm
---

> A good design system provides cost effective and consistent experiences across multiple platforms while providing a toolset to solve problems quickly.

---

# Design Systems

- Modules architecture
- Components-oriented
- Methodology
- Manifesto & Systemic Design

---
layout: punch
class: sm
---

A Design System is a <br>
**collaboration** tool for both <br>
Designers, Developers, Product engineers <br>
to offer a <mark>consistent experience</mark>

---

# From a Developer PoV

<Giphy id="g01ZnwAUvutuK8GIQn" />

---
layout: media
---

# It's a living styleguide

<Figure src="./img/kss-demo-1.png" caption="Jaco app KSS Styleguide" />

---

## Living styleguide

- Serve as a UI documentation
- Visualize states of elements
- Give use-cases and live examples
- Generated from code

---
layout: media
---

# It's a Demo Lab

<Figure src="./img/patternlab-demo.png" caption="PatternLab Atomic Design Demo" />

---

## Demo Lab

- Sandbox Atoms and Molecules
- Playground for templates
- Visualize regressions and UI glitches
- Allow to test global UX

---
layout: media
---

# It's a living documentation

<Figure src="./img/storybook-screenshot.png" caption="Storybook.js UI" />

---

# Living documentation

- List all available components
- Share stories with your team
- Collect feedback
- Generated from code

---

# There's more...

- Unit tests
- A11y tests
- UI changes
- *etc.*

---
layout: leaf
---

# The weird side

---

<Giphy id="3oEjI1erPMTMBFmNHi" caption="Brace youselves, tools are coming" />

---
layout: punch
---

As developers, <br>
we write <mark>code</mark> <br>
<small class="text-2xl leading-tight">and we're often not that good designers</small>

---
layout: media
---

# We organize components...

<Giphy id="PlnQNcQ4RYOhG" />

---

# ... using multiple technologies

- HTML
- JS(x), TS(x)
- CSS, (pre|post)-processors

```vue
<template>
  <p>{{ greeting }} World!</p>
</template>

<script>
module.exports = {
  data: function() {
    return {
      greeting: "Hello"
    };
  }
};
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
```

---

# ... and multiple frameworks

- React.js
- Vue.js
- Svelte
- LitElement
- Sass
- Tailwindcss
- Chakra
- *etc.*

---
layout: media
---

<Giphy id="xsATxBQfeKHCg" caption="Developing interfaces, the right way" />

---

# As a developer, I...

- use components freely
- rely on multiple frameworks
- am able to switch at any time
- give feedback to my teammates

---

# Kepping the good work

- Style consistency
- Demos and Live stories
- Documentation

---

## Styleguide consistency

```scss
// A button suitable for giving stars to someone.
//
// :hover             - Subtle hover highlight.
// .stars-given       - A highlight indicating you've already given a star.
// .stars-given:hover - Subtle hover highlight on top of stars-given styling.
// .disabled          - Dims the button to indicate it cannot be used.
//
// Styleguide 2.1.3.
a.button.star{
  …
  &.star-given{
    …
  }
  &.disabled{
    …
  }
}
```

---

## Build the styleguide

- Generated from the code
- Can exploit templates from components
- Display variations and states

---

## Live stories

```ts
// Button.stories.tsx

export const Primary: React.VFC<{}> = () => (
  <Button background="#ff0" label="Button" />
);
export const Secondary: React.VFC<{}> = () => (
  <Button background="#ff0" label="😄👍😍💯" />
);
export const Tertiary: React.VFC<{}> = () => (
  <Button background="#ff0" label="📚📕📈🤓" />
);
```

---

## Build the stories

- Render live example
- Allow complex rendering
- Offer a playground to `args`

---

## Documentation

- Generated from docblocks
- Support advanced formats (MD(X), ...)
- Explain the UX

---
layout: punch
class: sm
---

<mark>Separation of concerns</mark> <br>
is the only way not to **mess** <br>
your entire Design System

---

# Sharing

- across projects (UI library)
- as standalone components
- as resources for your team(s)

---
layout: punch
---

You can do it!

---
layout: media
---

# By hand, if you've got enough time

<Giphy id="ChX3hzy5CkXsI" />

---
layout: media
---

# With a dedicated team, if you're lucky

<Giphy id="ghutdpgRkhkxq" />

---
layout: punch
class: sm
---

Time to upgrade our Devtools 💪

> Developers are users just like you

---
layout: media
---

# Backlight

<Figure src="./img/backlight.png" />
