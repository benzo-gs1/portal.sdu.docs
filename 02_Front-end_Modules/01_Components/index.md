# Components 🧱

This document describes Vue.js components hierarchy and their meaning.

Components are prefixed like:

- TheComponent - The prefix describes component that is used only once
- BaseComponent - Base prefix describes component that is wrapped above some ui tool (buttons, forms, etc...)

## Hierarchy 🏗️

Hierarchy applies only at router components that are being used by routing mechanisms. Such components are located at (/views folder).

- [App](./01_App.md) - Root, contains top-level router-view
  - [TheAuth](./02_TheAuth.md)
  - [TheHomepage](./03_TheHomepage.md)
