## Engineering Workflow

| Stage | Command | Config File | Confidence |
|------------|----------------------|-------------|------------|
| install | `npm ci` | package.json | 0.97 |
| build | `npm run build` | package.json | 0.97 |
| dev | `npm run dev` | package.json | 0.97 |
| lint | `npm run lint` | package.json | 0.90 |
| type_check | `npx tsc --noEmit` | tsconfig.json | 0.90 |

## Dependency Guide

This project is a **TypeScript** application managed with **npm**.
Full dependency purpose and usage entries are catalogued in [`dependencies_overview.md`](./dependencies_overview.md).

| Package | Purpose Summary |
|---|---|
| `next` | React framework for full-stack web apps (SSR, SSG, routing, API routes) |
| `react` | JavaScript library for building component-based user interfaces |
| `react-dom` | DOM renderer for React; mounts and manages component trees in the browser |
| `react-markdown` | Renders Markdown strings as safe React elements with plugin support |

See `dependencies_overview.md` for detailed purpose and usage documentation.

## Business Logic Domain

This example is a self-contained frontend demo with no registered data models. Here is the business domain summary based on all the content reviewed:

This codebase is an embeddable AI-powered chat support widget built on top of the Onyx platform's APIs. It enables website owners to integrate a floating conversational chatbot that creates chat sessions, streams AI-generated responses in real time, and renders answers as Markdown. The domain centers on **AI-assisted customer support and conversational search**, leveraging Onyx's retrieval-augmented generation (RAG) backend — where each user message triggers a document retrieval search and returns an AI-synthesized answer. It is intended as a lightweight, configurable reference implementation for teams wanting to embed Onyx's enterprise knowledge assistant into their own web properties.

> No data models are registered for this package. See [`business_logic_references.md`](./business_logic_references.md) for full domain reference notes.

## App Interfaces

No inbound, outbound, or internal interface constructs are registered for this package.

See [`app_interfaces.md`](./app_interfaces.md) for full interface reference notes.