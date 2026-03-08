# Dependencies Overview

This file is the source-of-truth dependency catalog for the `widget` example project.
Primary language: **TypeScript** | Package manager: **npm**

---

## next

**Purpose:**
Next.js is a React framework for building full-stack web applications, using React Components for user interfaces alongside powerful additional features. It enables creation of high-quality web applications by extending the latest React features and integrating Rust-based JavaScript tooling for performance.

**Usage:**
Next.js provides capabilities such as server-side rendering, static site generation, file-based routing, and API routes, all with built-in TypeScript support out of the box. It supports advanced features like the App Router, React Server Components, middleware, image optimization, and seamless deployment via Vercel.

---

## react

**Purpose:**
React is a JavaScript library for building user interfaces. It makes it painless to create interactive UIs by letting you design simple views for each state in your application, efficiently updating and rendering just the right components when your data changes.

**Usage:**
React is component-based, allowing you to build encapsulated components that manage their own state and compose them to create complex UIs. It supports TypeScript natively (via `@types/react`), offering typed hooks, props, refs, and event handling for robust, type-safe frontend development.

---

## react-dom

**Purpose:**
This package serves as the entry point to the DOM and server renderers for React. It is intended to be paired with the generic React package and provides the methods needed to mount and manage React component trees in a browser DOM environment.

**Usage:**
react-dom exposes core APIs such as `createRoot` (and `hydrateRoot`) for rendering React component trees into browser DOM nodes, as well as utilities like `flushSync` and `createPortal` for fine-grained DOM control. It also includes a `react-dom/server` sub-package for server-side rendering via `renderToString` and streaming APIs, enabling full-stack React applications in TypeScript projects.

---

## react-markdown

**Purpose:**
A React component that safely renders Markdown strings as React elements, following CommonMark and optionally GitHub Flavored Markdown (GFM) specifications.

**Usage:**
It renders actual React elements instead of using `dangerouslySetInnerHTML`, and allows you to define fully custom components to replace default HTML tags (e.g., render a custom heading instead of `h1`). It supports a rich plugin ecosystem via `remark` and `rehype` plugins, enabling advanced capabilities such as syntax highlighting, math rendering, and more.