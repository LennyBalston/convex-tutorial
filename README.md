# Convex tutorial chat app

This repo is a minimal real-time chat app built by following the official Convex walkthrough: [Convex Tutorial: A chat app](https://docs.convex.dev/tutorial/). The tutorial explains how the backend (`convex/`), queries, mutations, and React client fit together.

## Prerequisites

- [Node.js](https://nodejs.org/) **18 or later**

## Getting started locally

1. Install dependencies:

   ```bash
   npm install
   ```

2. Start development (Vite frontend and `convex dev` run in parallel). On the first run, `convex init` runs so you can link or create a Convex project:

   ```bash
   npm run dev
   ```

3. Open the app at [http://localhost:5173](http://localhost:5173).

Keep `npm run dev` running while you work so the frontend and backend stay in sync.
