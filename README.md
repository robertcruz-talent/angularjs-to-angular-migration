# AngularJS to Angular Migration Demo

This project demonstrates a practical, real-world approach for migrating an
existing AngularJS 1.x application to modern Angular. It focuses on an
incremental hybrid strategy that allows AngularJS and Angular to run together
during the transition, reducing risk and avoiding a full rewrite.

---

## Overview

Large legacy AngularJS applications often need modernization without breaking
existing features. This demo provides a complete reference for:

- preparing your AngularJS codebase for migration
- converting components and services
- running AngularJS and Angular in hybrid mode
- gradually moving routing, templates, and business logic to Angular
- safely deploying a hybrid application to production

This approach enables teams to migrate at their own pace while keeping the app
stable.

---

## Prerequisites Before Migration

Before using this demo as a reference, ensure your current AngularJS application
is prepared. Your project **must be organized by feature sections**, where each
section contains:

- templates
- controllers / components
- services
- styles
- tests

Proper structure is critical for a smooth migration.

---

## Required Preparation Steps

1. **Convert controllers and directives to AngularJS 1.5+ components.**

   - Use ES6 classes.
   - Remove `$scope`, `$rootScope`, shared scopes, and global state.

2. **Remove bad patterns.**

   - No `$parent` references.
   - No heavy `$watch` logic.
   - Replace data observers with component inputs/callbacks.

3. **Convert all JavaScript files to TypeScript (.ts).**  
   Improves type safety and prepares for Angular.

4. **Update component template paths to use relative paths.**

5. **Create central entry points** such as:

   - `index.ts` for imports
   - `vendors.ts` for vendor libraries

6. **Introduce Webpack** to replace older build tools such as Gulp or Grunt.

7. **Ensure AngularJS version is 1.5+.**  
   AngularJS components were added in 1.5, making migration easier.

---

## What This Demo Shows

After your AngularJS project is prepared, this repository helps you understand:

### ✔ Bootstrapping

How to bootstrap an AngularJS application inside Angular using `UpgradeModule`.

### ✔ Component Upgrades

How to convert AngularJS 1.5+ components into Angular components.

### ✔ Service Migration

How to convert AngularJS services into Angular `@Injectable` services while
maintaining compatibility.

### ✔ Interoperability

How Angular code can call AngularJS services and vice-versa during hybrid mode.

### ✔ Routing Migration

How to move routing logic from AngularJS routing to Angular Router without
breaking existing flows.

### ✔ Testing

How to maintain AngularJS Jasmine tests while adding Angular unit tests.

### ✔ Production Build

How to prepare an AOT-optimized build that supports hybrid execution in
production.

Teams can continue working in Angular while slowly removing AngularJS code
section by section.

---

## Tech Stack

- AngularJS 1.5+
- Angular
- TypeScript
- Webpack
- Optional: Bootstrap, Font Awesome, Lodash

---

## When to Use This Demo

Use this project if you have:

- a mid-to-large AngularJS application
- no ability to rewrite the system from scratch
- multiple teams needing to continue feature development
- a need to upgrade gradually without downtime

This demo is ideal for planning, training, and staging a real migration.

---

## Purpose

This repository serves as a complete reference for teams responsible for
modernizing legacy AngularJS codebases. It focuses on a safe, scalable, and
maintainable migration approach based on industry best practices.

By following the outlined structure and techniques, you can move your
application into modern Angular step by step—without breaking production.

## Known Issues

- AngularJS directive compatibility issues during hybrid mode
- Pending full migration of services to Angular

## Future Improvements

- Add Jest tests
- Add Angular Routing
