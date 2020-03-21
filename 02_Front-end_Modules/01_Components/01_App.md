# App component 🏙️

Root, contains 1 level of router-view.

Table of contents:

- [App component 🏙️](#app-component-%f0%9f%8f%99%ef%b8%8f)
  - [Hooks ⚓️](#hooks-%e2%9a%93%ef%b8%8f)
    - [created()](#created)

## Hooks ⚓️

### created()

When created, we check local token to be valid sending api call.

If it's valid, router.push to [TheHomepage](./03_TheHomepage.md)

If it's not, router.push to [TheAuth](./02_TheAuth.md)
