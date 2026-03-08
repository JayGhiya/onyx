# Dependencies Overview

> **Source of truth** for all third-party dependency purpose and usage documentation in the `web` package.
> Primary language: **TypeScript** · Package manager: **npm**

---

## @emotion/stylis

**Purpose:** A custom build of Stylis, a lightweight CSS preprocessor used internally by the Emotion CSS-in-JS library to process and transform CSS styles at runtime.

**Usage:** It parses and processes CSS strings, handling nested selectors, vendor prefixing, and media queries to produce valid, browser-compatible CSS output. As a tailored fork of the Stylis preprocessor, it is optimized for integration within the Emotion ecosystem, powering style compilation for packages like `@emotion/cache`.

---

## @headlessui/react

**Purpose:** Completely unstyled, fully accessible UI components for React, designed to integrate beautifully with Tailwind CSS.

**Usage:** It provides a rich set of accessible, behavior-driven components — including Dialog, Listbox, Combobox, Popover, Menu, and more — that handle complex interaction patterns like focus management, keyboard navigation, and ARIA attributes out of the box. Because all components are entirely unstyled, developers retain full control over appearance and can apply any custom or Tailwind CSS styles without fighting opinionated defaults.

---

## @headlessui/tailwindcss

**Purpose:** A complementary Tailwind CSS plugin for Headless UI that enables styling based on component state via custom data-attribute modifiers (e.g., `ui-open:*`, `ui-active:*`).

**Usage:** It extends Tailwind CSS with custom variant modifiers that map to Headless UI's internal state attributes, allowing developers to conditionally apply utility classes when components are open, active, selected, or disabled. It can be configured with a custom prefix (e.g., `ui`) and integrated directly into `tailwind.config.js` as a standard Tailwind plugin.

---

## @phosphor-icons/react

**Purpose:** A clean and flexible icon family for React, providing over 9,000 type-safe icon components from the Phosphor Icons family. Each icon is an SVG-based React component with a simple and intuitive API for styling.

**Usage:** Icons can be individually imported as React components and customized with props such as `size`, `color`, `weight` (e.g., thin, light, regular, bold, fill, duotone), and `mirrored`. The library leverages React's Context API via a `IconContext` provider, allowing default styles to be applied globally across all icons in a subtree.

---

## @sentry/nextjs

**Purpose:** The official Sentry SDK for Next.js, enabling error monitoring, performance tracing, and logging across client, server, and edge runtimes in Next.js applications.

**Usage:** It automatically captures errors, exceptions, and performance traces from all Next.js runtimes (browser, Node.js server, and edge), and integrates seamlessly via a setup wizard that configures `sentry.client.config.ts`, `sentry.server.config.ts`, and instrumentation hooks. It supports TypeScript natively and provides features such as distributed tracing, session replay, source map uploads, and customizable sampling rates for fine-grained observability.

---

## @sentry/tracing

**Purpose:** Sentry's Performance Monitoring package for JavaScript/TypeScript that enables distributed tracing across frontend and backend services. It automatically tracks software performance by measuring metrics like throughput, latency, and the impact of errors across multiple systems.

**Usage:** The package provides core primitives such as transactions and spans to instrument application code, along with built-in integrations like `BrowserTracing` for automatic page load and navigation performance tracking. It integrates seamlessly with other Sentry SDKs to enable end-to-end distributed tracing, configurable sampling rates, and Web Vitals monitoring.

---

## @stripe/stripe-js

**Purpose:** A loading wrapper for Stripe.js that ensures the Stripe.js script is loaded asynchronously and securely from Stripe's servers. It also includes first-class TypeScript declarations (supporting TypeScript >= 3.1) for the full Stripe.js browser-side API.

**Usage:** It exposes the `loadStripe` utility function, which lazily loads Stripe.js and returns a `Promise` resolving to a `Stripe` instance, enabling payments, Stripe Elements (pre-built UI components), and PaymentIntents within web apps. The bundled TypeScript type declarations cover all Stripe.js objects and methods, always tracking the latest Stripe API version to provide full type safety in TypeScript projects.

---

## @tailwindcss/container-queries

**Purpose:** A plugin for Tailwind CSS v3.2+ that provides utilities for CSS container queries, enabling styles to respond to the size of a parent element rather than the entire viewport.

**Usage:** It introduces the `@container` class to mark an element as a container, along with responsive variant prefixes like `@sm:`, `@md:`, `@lg:`, and `@xl:` to conditionally apply styles based on that container's size. It also supports named containers and arbitrary container size values for fine-grained, component-level responsive design in TypeScript-based Tailwind projects.

---

## @tanstack/react-table

**Purpose:** Headless UI library for building powerful tables and data grids for React, written in TypeScript. It provides all the logic, state management, and types needed for tables without rendering any DOM elements, giving developers full control over markup and styles.

**Usage:** @tanstack/react-table offers a comprehensive set of features including sorting, filtering, pagination, grouping, and column definitions, all managed through a flexible and composable API via the `useReactTable` hook. It is fully headless and framework-agnostic at its core, making it compatible with any UI component library or custom styling solution in TypeScript-based React projects.

---

## autoprefixer

**Purpose:** Autoprefixer is a PostCSS plugin that parses CSS and automatically adds vendor prefixes to CSS rules using values from Can I Use, based on current browser popularity and property support.

**Usage:** It integrates seamlessly into PostCSS-based build pipelines (e.g., webpack, Vite, esbuild) to handle cross-browser compatibility by inserting the appropriate `-webkit-`, `-moz-`, `-ms-`, and other vendor prefixes. It also removes outdated or unnecessary prefixes, keeping stylesheets clean and aligned with modern browser standards.

---

## class-variance-authority

**Purpose:** A TypeScript-first library (CVA) for creating and managing class name variants for UI components, eliminating the pain of manually matching CSS classes to props and maintaining their types.

**Usage:** CVA provides a `cva()` function that lets you define base styles alongside structured `variants`, `compoundVariants`, and `defaultVariants` for building type-safe, reusable component styling APIs. It also exposes the `VariantProps` TypeScript helper to automatically extract and infer variant prop types directly from a CVA-constructed function.

---

## clsx

**Purpose:** A tiny (239B) utility for constructing `className` strings conditionally. It accepts a mix of strings, arrays, and objects to produce a single, clean class name string.

**Usage:** clsx supports multiple input types — including strings, objects (where keys are class names and values are booleans), and arrays — allowing for expressive conditional class composition. It ships with built-in TypeScript type declarations, offering type-safe class name construction with no additional `@types` package required.

---

## cmdk

**Purpose:** ⌘K is a fast, unstyled command menu React component that can also be used as an accessible combobox. It automatically filters and sorts rendered items and ships with built-in TypeScript type declarations.

**Usage:** cmdk provides a fully composable API that lets you wrap items in other components or static JSX, with support for grouping, separators, and dialog-based elevation. It includes built-in ARIA roles, keyboard navigation, and live filtering so results update instantly as the user types.

---

## cookies-next

**Purpose:** A versatile cookie management library for Next.js applications, supporting both client-side and server-side operations. It is compatible with Next.js 13+ App Router, Server Components, API routes, and server-side rendering.

**Usage:** It provides a unified API with functions such as `getCookie`, `setCookie`, `deleteCookie`, and `getCookies`, usable across both client and server contexts via dedicated `cookies-next/client` and `cookies-next/server` imports. The library is TypeScript compatible and is designed to be lightweight and straightforward, making cookie management seamless throughout the entire Next.js application lifecycle.

---

## date-fns

**Purpose:** date-fns is a modern JavaScript/TypeScript date utility library that provides the most comprehensive, yet simple and consistent toolset for manipulating JavaScript dates in a browser & Node.js.

**Usage:** It offers over 200 pure, immutable utility functions for formatting, parsing, comparing, and manipulating dates, with TypeScript typings bundled directly in the package and always kept up-to-date. Each function is individually importable, enabling tree-shaking for optimized bundle sizes in any JavaScript or TypeScript project.

---

## @dnd-kit/core

**Purpose:** The foundational package of the dnd-kit library — a lightweight, performant, and accessible drag-and-drop toolkit for React. It provides the core primitives including `DndContext`, `useDraggable`, `useDroppable`, sensors, and collision detection algorithms.

**Usage:** It exposes the `DndContext` provider that coordinates all draggable and droppable elements within a React tree, along with hooks like `useDraggable` and `useDroppable` for composing custom drag-and-drop interactions. Sensor abstractions (Mouse, Touch, Keyboard) and collision detection strategies allow fine-grained control over how drag events are initiated and resolved.

---

## docx-preview

**Purpose:** docx-preview is a TypeScript/JavaScript library that renders DOCX files directly into HTML for in-browser previewing of Word documents.

**Usage:** It exposes a primary `renderAsync` function that accepts a DOCX file (as a Blob, ArrayBuffer, or similar) and renders its content — including paragraphs, tables, lists, and formatting — into a specified HTML container element. The library ships with built-in TypeScript type declarations and offers configurable rendering options to control how document styles, page layout, and other DOCX features are translated to HTML.

---

## favicon-fetch

**Purpose:** A package that instantly gives you a URL for any website's favicon, powered by the Icon Horse service.

**Usage:** It provides a simple utility function that, given any website URL, returns the corresponding favicon URL by leveraging the Icon Horse favicon-resolution service. It can be installed via npm or yarn and used in TypeScript/JavaScript projects with a straightforward require or import call.

---

## formik

**Purpose:** Formik is a small library that helps you with the 3 most annoying parts of building forms in React: getting values in and out of form state, validation and error messages, and handling form submission. Its source code is written in TypeScript, so types are always up-to-date.

**Usage:** Formik provides a cohesive API to manage form state, handle field-level and form-level validation, and control submission lifecycle — all without relying on external state management libraries like Redux or MobX. It offers first-class TypeScript support with generic type signatures (e.g., `useFormik<MyValues>()`) that provide full type safety across form values, errors, and touched fields.

---

## highlight.js

**Purpose:** highlight.js is a syntax highlighting library for code blocks, supporting multiple programming languages, automatic language detection, and customizable themes — with zero external dependencies.

**Usage:** It works both in the browser and on the server (Node.js), and can integrate via CDNs, ES6 modules, Vue plugins, or web workers. Core capabilities include automatic language detection, a wide range of supported languages, and theming support to render beautifully highlighted code blocks.

---

## js-cookie

**Purpose:** A simple, lightweight JavaScript API for handling browser cookies, compatible with TypeScript via the `@types/js-cookie` package.

**Usage:** js-cookie provides an intuitive API with `Cookies.set()`, `Cookies.get()`, and `Cookies.remove()` methods for creating, reading, and deleting cookies with customizable attributes such as expiry, path, domain, and secure flags. It supports ES module and UMD builds for broad bundler compatibility, and allows global or per-call configuration of cookie attribute defaults via `withAttributes()`.

---

## katex

**Purpose:** KaTeX is a fast, easy-to-use JavaScript library for TeX math rendering on the web. It renders math synchronously without requiring page reflow, and is fully self-contained with no external dependencies.

**Usage:** KaTeX provides two core API methods — `katex.render` to render LaTeX math directly into a DOM element, and `katex.renderToString` to produce an HTML string for server-side or custom rendering scenarios. It supports a wide range of TeX functions, configurable display modes, persistent macros, and structured error handling via `katex.ParseError`.

---

## linguist-languages

**Purpose:** linguist-languages provides GitHub Linguist's `languages.yml` data as a structured, importable JSON format for use in Node.js/TypeScript projects. It exposes metadata for hundreds of programming languages as recognized by GitHub's language detection library.

**Usage:** The package gives developers programmatic access to language definitions including file extensions, aliases, color codes, and type classifications (e.g., programming, markup, data). It is commonly used in TypeScript projects to perform language detection, syntax highlighting configuration, or any feature requiring rich, up-to-date language metadata derived from GitHub's Linguist.

---

## lodash

**Purpose:** A modern JavaScript utility library delivering modularity, performance & extras. Lodash makes JavaScript easier by taking the hassle out of working with arrays, numbers, objects, strings, and more.

**Usage:** Lodash provides a rich set of utility functions for common programming tasks such as array manipulation, object transformation, deep cloning, debouncing, throttling, and functional programming patterns like map, filter, and reduce. When used in TypeScript projects, it pairs with the `@types/lodash` type definitions package to enable full compile-time type safety and IntelliSense support.

---

## lowlight

**Purpose:** Virtual syntax highlighting for virtual DOMs and non-HTML things, built on top of highlight.js. It processes code and returns a hast (HTML Abstract Syntax Tree) rather than raw HTML strings.

**Usage:** It exposes a rich API including `highlight(language, value)` for language-specific highlighting and `highlightAuto(value)` for automatic language detection across hundreds of supported grammars. Additional utilities like `register`, `registerAlias`, and `listLanguages` allow full control over language definitions and aliases.

---

## lucide-react

**Purpose:** React components for Lucide icons that integrate seamlessly into React applications, with full TypeScript support. It is built with ES Modules, making it completely tree-shakable.

**Usage:** Each icon in the library can be individually imported as a React component, rendering an inline SVG element that is easy to use in JSX. Icons support customizable props for size, color, stroke width, and other SVG attributes to match any UI design.

---

## mdast-util-find-and-replace

**Purpose:** A utility that lets you find patterns (string or RegExp) in mdast text nodes and replace them with new nodes. It is part of the syntax-tree/unified ecosystem for working with Markdown Abstract Syntax Trees (mdast).

**Usage:** It traverses all text nodes in an mdast tree, matching against provided string or regular expression patterns and invoking replacement handlers to return new mdast nodes. It is commonly used for transformations like converting mention patterns (e.g., `/@username/`) into link nodes, enabling rich mdast modifications with regex-driven rules.

---

## motion

**Purpose:** Motion (previously Framer Motion) is a fast, production-grade web animation library for JavaScript, React, and Vue. It provides a simple yet powerful API for creating smooth UI animations with a tiny footprint.

**Usage:** Motion features a hybrid animation engine that combines the flexibility of JavaScript animations with the performance of native browser APIs, enabling 120fps, GPU-accelerated animations. It supports a wide range of animation capabilities including scroll animations, layout animations, gestures (drag, hover, tap), spring physics, and powerful timeline sequencing.

---

## next

**Purpose:** Next.js is a React framework for building full-stack web applications, providing additional features and optimizations on top of React Components. It automatically configures lower-level tools like bundlers and compilers for a streamlined developer experience.

**Usage:** Next.js offers powerful capabilities including hybrid static and server-side rendering (SSR), file-based routing, API routes, and built-in TypeScript support. It comes with automatic code splitting, image optimization, and production-ready performance optimizations out of the box.

---

## next-themes

**Purpose:** An abstraction for themes in your React/Next.js app, enabling perfect dark mode in 2 lines of code with support for system preferences and any custom theme without any flash on load.

**Usage:** It provides a `ThemeProvider` component that wraps your application to manage theme state, persistence (via localStorage), and DOM updates — supporting class or data-attribute selectors and syncing themes across tabs. The `useTheme` hook gives components easy access to the current theme and a setter, with built-in support for `prefers-color-scheme`, forced page-level themes, and Next.js App Router compatibility.

---

## postcss

**Purpose:** PostCSS is a tool for transforming styles with JavaScript plugins. These plugins can lint your CSS, support variables and mixins, transpile future CSS syntax, inline images, and more.

**Usage:** PostCSS provides a powerful plugin-based architecture that parses CSS into an Abstract Syntax Tree (AST), allowing plugins to programmatically read and transform styles. It supports a rich ecosystem of plugins enabling capabilities such as auto-prefixing, future CSS syntax transpilation, linting, and CSS module support.

---

## posthog-js

**Purpose:** posthog-js is the official JavaScript/TypeScript SDK for PostHog, an all-in-one product analytics platform. It allows you to automatically capture usage data and send custom events from your web application to PostHog.

**Usage:** posthog-js provides powerful features including autocapture of clicks, form submissions, and page views, along with manual custom event tracking, user identification, and group analytics. It also supports advanced capabilities such as feature flags, A/B experiments, session recording, and heatmaps directly from the browser.

---

## pptxgenjs

**Purpose:** PptxGenJS is a JavaScript/TypeScript library that lets you generate professional PowerPoint presentations programmatically — directly from Node, React, Vite, Electron, and more.

**Usage:** It provides a powerful, concise API to create slides and add rich content elements such as text, images, charts, shapes, and tables with full TypeScript type definitions included. Presentations can be exported in multiple ways, and the library supports modern environments including Angular, React, and ES6/TypeScript workflows.

---

## Radix UI React Primitives

**Purpose:** An open-source, low-level UI component library for building high-quality, accessible design systems and web apps, with a focus on accessibility, customization, and developer experience.

**Usage:** The library provides a comprehensive family of unstyled, composable React primitives — including `@radix-ui/react-accordion`, `@radix-ui/react-avatar`, `@radix-ui/react-collapsible`, `@radix-ui/react-dialog`, `@radix-ui/react-dropdown-menu`, `@radix-ui/react-hover-card`, `@radix-ui/react-label`, `@radix-ui/react-menubar`, `@radix-ui/react-popover`, `@radix-ui/react-radio-group`, `@radix-ui/react-scroll-area`, `@radix-ui/react-select`, `@radix-ui/react-separator`, `@radix-ui/react-slider`, `@radix-ui/react-slot`, `@radix-ui/react-tabs`, and `@radix-ui/react-tooltip` — each delivered as an independently installable package. Every primitive ships with built-in WAI-ARIA compliance, keyboard navigation, and full TypeScript typings, enabling teams to apply any custom styling layer on top without sacrificing accessibility or behavior.

---

## react

**Purpose:** React is the library for web and native user interfaces, enabling developers to build UIs out of individual, reusable pieces of code called components.

**Usage:** React provides a declarative, component-based model for constructing interactive user interfaces, with a virtual DOM that efficiently updates and renders only the necessary components when data changes. It offers a rich set of built-in Hooks (such as useState, useEffect, and useContext) that allow functional components to manage state, handle side effects, and share logic across an application.

---

## react-datepicker

**Purpose:** A simple and reusable datepicker component for React, crafted by HackerOne. It provides an accessible, highly configurable calendar UI for selecting dates and times in React applications.

**Usage:** react-datepicker supports a wide range of features including date range selection, time picking, locale-based internationalization via date-fns, and customizable date filtering. It offers flexible configuration through props such as minDate, maxDate, inline display, portal rendering, and custom input components, making it adaptable to diverse use cases.

---

## react-day-picker

**Purpose:** DayPicker is a customizable date picker component for React, used to add date pickers, calendars, and date inputs to web applications.

**Usage:** It provides flexible, accessible calendar UI components with support for single date, multiple date, and date range selection modes. Built with full TypeScript support, it offers extensive customization options including custom styles, modifiers, locale settings, and controlled/uncontrolled input integration.

---

## react-dom

**Purpose:** The `react-dom` package contains methods that are only supported for web applications running in the browser DOM environment. It provides DOM-specific methods for rendering and managing React components within the browser.

**Usage:** It exposes two primary entry points: `react-dom/client` for rendering React component trees on the client side, and `react-dom/server` for server-side rendering. It also provides escape-hatch utilities like `createPortal` for rendering outside the normal React tree and `flushSync` for forcing synchronous state updates.

---

## react-dropzone

**Purpose:** react-dropzone is a simple HTML5 drag-and-drop zone library for React.js that provides a customizable file upload component with drag-and-drop functionality.

**Usage:** It exposes a `useDropzone` hook that returns `getRootProps` and `getInputProps` helpers to easily wire up drag-and-drop and click-to-browse file selection on any container element. It supports TypeScript out of the box with precise type definitions, and offers configurable options such as accepted file types, multiple file selection, and file validation callbacks.

---

## react-icons

**Purpose:** react-icons is a library that provides SVG React icons from popular icon packs (such as Font Awesome, Material Design, Bootstrap Icons, and more) using ES6 imports, with built-in TypeScript type declarations.

**Usage:** It allows developers to import only the icons they need as individual React components, enabling automatic tree-shaking and optimized bundle sizes. Each icon can be easily customized via props such as size, color, and className, making them seamlessly composable within any React or TypeScript project.

---

## react-loader-spinner

**Purpose:** react-loader-spinner provides a broad collection of production-ready SVG loading spinner components for React.js applications, designed to indicate async wait operations before data loads into the view. It is lightweight, customizable, and TypeScript-ready.

**Usage:** The library offers a wide variety of spinner types (e.g., ThreeDots, Oval, RotatingTriangles) that can be easily dropped into any React component with configurable props such as color, height, width, and aria labels. It supports both plain JavaScript and strict TypeScript projects, making it straightforward to theme and integrate loading experiences across different application setups.

---

## react-markdown

**Purpose:** A React component that safely renders Markdown strings as React elements, following CommonMark and optionally GitHub Flavored Markdown (GFM) specifications.

**Usage:** It renders actual React elements instead of using `dangerouslySetInnerHTML`, and allows developers to define fully custom components for any Markdown element (e.g., replacing `h1` with a custom heading). It supports extensibility through the remark and rehype plugin ecosystems, enabling advanced features such as syntax highlighting, math rendering, and more.

---

## react-select

**Purpose:** A flexible and beautiful Select Input control for ReactJS with multiselect, autocomplete, and async/ajax support.

**Usage:** react-select provides a highly customizable dropdown/select component for React, supporting features like multi-select, async option loading, search/autocomplete, and full TypeScript typings out of the box. It exposes granular component-level customization and a style API, enabling developers to tailor every part of the select control to match their application's design system.

---

## recharts

**Purpose:** Recharts is a redefined chart library built with React and D3, designed to help developers write charts in React applications without any pain. It is built on native SVG support, keeping dependencies minimal while following declarative component principles.

**Usage:** Recharts provides a suite of composable, declarative React components — such as LineChart, BarChart, PieChart, and more — that can be easily assembled and customized to build a wide range of data visualizations. It includes built-in TypeScript type declarations, making it fully type-safe and seamlessly integrable into TypeScript-based React projects.

---

## rehype-highlight

**Purpose:** A unified (rehype) plugin to perform syntax highlighting on code blocks using lowlight (backed by highlight.js). It bundles 37 common languages by default and supports up to 190 languages via additional registration.

**Usage:** rehype-highlight operates on `<code>` elements in the HTML syntax tree and applies highlight.js-compatible CSS class-based syntax highlighting through the lowlight library. It integrates seamlessly into unified/rehype processing pipelines, making it ideal for highlighting code in Markdown or HTML content transformations in TypeScript projects.

---

## rehype-katex

**Purpose:** A rehype plugin to transform inline and block math elements in HTML into beautifully rendered mathematical notation using KaTeX.

**Usage:** It integrates into the unified/rehype processing pipeline to render math expressions found in HTML nodes (typically produced by `remark-math`) via the KaTeX engine. It supports both inline and block-level math, and accepts KaTeX options for customizing output such as display mode, macro definitions, and error handling.

---

## rehype-sanitize

**Purpose:** A rehype plugin to sanitize HTML by cleaning hast (HTML abstract syntax trees), recommended for use whenever authors or plugins are not fully trusted. It is built on hast-util-sanitize and follows GitHub-style sanitization rules by default.

**Usage:** It integrates into the unified/rehype processing pipeline via `.use(rehypeSanitize[, schema])`, stripping any HTML elements or attributes not explicitly permitted by a configurable schema. The default schema mirrors GitHub's sanitization rules, but custom schemas can be provided to precisely control which tags and attributes are allowed.

---

## rehype-stringify

**Purpose:** A unified (rehype) plugin that defines how to take an HTML syntax tree (hast) as input and turn it into serialized HTML output. It is a core component of the rehype ecosystem, enabling HTML serialization as the final step in a processing pipeline.

**Usage:** rehype-stringify is built on top of `hast-util-to-html`, converting hast syntax trees into HTML strings, and supports options for controlling character references, formatting, and output structure. It integrates seamlessly with other unified/rehype plugins, making it the standard serialization step when building HTML transformation pipelines in TypeScript projects.

---

## remark-gfm

**Purpose:** A remark plugin to support GitHub Flavored Markdown (GFM), enabling extensions such as autolink literals, footnotes, strikethrough, tables, and tasklists. It is useful when you want to match GitHub's own Markdown rendering behavior in your project.

**Usage:** It integrates with the unified/remark ecosystem via `unified().use(remarkGfm)`, extending the Markdown parser and compiler to handle GFM-specific syntax not covered by standard Markdown. Core capabilities include rendering pipe tables, ~~strikethrough~~ text, `- [ ]` task list items, footnotes, and bare URL autolinking directly from Markdown source.

---

## remark-math

**Purpose:** A remark plugin to parse and stringify math, enabling support for mathematical expressions written in LaTeX within Markdown documents.

**Usage:** It supports both inline math (using single `$` delimiters) and block-level math (using double `$$` delimiters), parsing them into dedicated AST nodes within the remark/unified pipeline. These AST nodes can then be processed by companion plugins such as `rehype-katex` or `rehype-mathjax` to render the mathematical notation in HTML output.

---

## semver

**Purpose:** The semantic version parser used by npm. It provides utilities for parsing, validating, and comparing version strings that follow the Semantic Versioning (SemVer) specification.

**Usage:** It offers a rich set of functions — including `semver.valid()`, `semver.satisfies()`, `semver.gt()`, `semver.lt()`, and `semver.coerce()` — for validating version strings, comparing version precedence, and checking versions against range constraints. TypeScript type definitions are available via `@types/semver`, making it fully compatible with TypeScript projects for managing and reasoning about dependency versioning at both runtime and type-check time.

---

## sharp

**Purpose:** sharp is a high performance Node.js image processing module — the fastest available for resizing JPEG, PNG, WebP, GIF, AVIF, and TIFF images. It is built on top of the libvips library to deliver speed and low memory usage.

**Usage:** sharp supports a wide range of image operations including resizing, cropping, rotation, format conversion, compositing, and metadata extraction through a fluent, chainable API. It also supports advanced capabilities such as splitting a single input stream into multiple processing pipelines and generating Deep Zoom image pyramids for use with tile-based map viewers.

---

## stripe

**Purpose:** The `stripe` Node.js library provides convenient access to the Stripe API from applications written in server-side JavaScript and TypeScript, enabling seamless integration with Stripe's payment processing platform.

**Usage:** It offers a full-featured API wrapper covering payments, subscriptions, customers, invoices, webhooks, and more, with first-class TypeScript types that always reflect the latest shape of the Stripe API. The library reduces boilerplate by providing promise-based methods for every Stripe resource, automatic pagination, idempotency support, and built-in webhook signature verification.

---

## swr

**Purpose:** SWR is a React Hooks library for data fetching that provides a minimal API with built-in caching, revalidation, and request deduplication. The name "SWR" is derived from the HTTP cache invalidation strategy `stale-while-revalidate`, keeping UI always fast and reactive.

**Usage:** The core `useSWR` hook accepts a key and a fetcher function, automatically managing requests, caching responses, and keeping data fresh with background revalidation. It offers full TypeScript support with type inference for data and error states, along with features like subscription-based updates, deduplication, and reusable data-fetching logic across React components.

---

## tailwind-merge

**Purpose:** A utility function to efficiently merge Tailwind CSS classes in JavaScript/TypeScript without style conflicts. It intelligently resolves class name collisions that arise when combining conditional or dynamic Tailwind classes.

**Usage:** The core `twMerge` function accepts multiple class name strings or arrays and returns a single, conflict-free merged class string by understanding Tailwind's utility class relationships. It supports full TypeScript typing, custom Tailwind configuration extensions, and handles edge cases like conditional classes, duplicate utilities, and overriding conflicting styles.

---

## tailwindcss-animate

**Purpose:** A Tailwind CSS plugin for creating beautiful animations. It extends Tailwind's utility classes with a rich set of animation utilities powered by CSS variables and keyframes.

**Usage:** It provides composable utility classes to control animation properties such as duration, delay, easing, direction, fill mode, and play state directly in your markup. Under the hood, it uses a CSS variable system as an intermediate layer between utility classes and keyframe animations, enabling flexible and declarative animation composition.

---

## uuid

**Purpose:** A JavaScript/TypeScript library for generating RFC 9562 (formerly RFC 4122) compliant UUIDs. It supports multiple UUID versions including v1 (timestamp-based), v4 (random), v5 (namespace/SHA-1), v6, and v7.

**Usage:** The library provides dedicated functions (e.g., `v1()`, `v4()`, `v5()`, `v6()`, `v7()`) to generate UUIDs suited for different use cases, from time-based to cryptographically random identifiers. TypeScript support is built-in (no need for `@types/uuid`), and it works across Node.js, browsers, and other modern JavaScript environments.

---

## vaul

**Purpose:** Vaul is an unstyled drawer component for React that can be used as a Dialog replacement on tablet and mobile devices.

**Usage:** It provides composable, headless components (such as Drawer, Drawer.Trigger, Drawer.Content, and Drawer.Overlay) that support gestures, snap points, nested drawers, and background scaling. The drawer can be controlled or uncontrolled, opened by default via a `defaultOpen` prop, and customized with options like `shouldScaleBackground` for smooth animated transitions.

---

## yup

**Purpose:** Yup is a schema builder for runtime value parsing and validation. Define a schema, transform a value to match, assert the shape of an existing value, or both — with extremely expressive schemas that allow modeling complex, interdependent validations or value transformations.

**Usage:** Yup provides a chainable, declarative API to define schemas for objects, strings, numbers, arrays, and more, with built-in support for custom validation rules, conditional logic, and value coercion. It integrates seamlessly with TypeScript via inferred static types from schemas, making it a popular choice for form validation (e.g., with React Hook Form or Formik) and API input validation.

---

## zustand

**Purpose:** Zustand is a small, fast, and scalable state management solution for React. It provides bear necessities for managing global state with a minimal and unopinionated API.

**Usage:** Zustand allows you to create stores using a simple `create()` function that holds state and actions, making global state accessible across components without boilerplate like reducers or context providers. It has full TypeScript support with type inference, enabling type-safe stores, middleware composition, and seamless integration into TypeScript React projects.