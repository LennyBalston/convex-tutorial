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

## Using the app

- **Who you are**: The header shows a random first name generated when you first load the page. It is stored in the browser’s session storage (key `tutorial_name`) so it stays stable for that tab; there is no sign-in.
- **Live updates**: The chat list subscribes to Convex, so new messages—including Wikipedia replies—show up without reloading.
- **What you see**: The backend returns the **50 most recent** messages, oldest-to-newest in the UI. Your own lines are styled differently from everyone else’s.
- **Sending**: Each send runs a Convex **mutation** that writes to the `messages` table. The `/wiki` command triggers extra work on the server after that insert (see below).

### `/wiki` in chat

In the message box, send a line that starts with `/wiki` followed by a space and a [Wikipedia](https://www.wikipedia.org/) article title (for example: `/wiki Convex database`). The app stores your message as usual, then the Convex backend calls the Wikipedia API, fetches the short introduction text for that title, and posts a follow-up message from **Wikipedia** with the summary. Titles can include spaces; the topic is everything after the first space. If the API has no extract for the title, the bot message may be empty or unexpected—try a slightly different article name.
