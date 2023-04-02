# Minesweeper

An HTML Canvas implementation of Minesweeper, plus eventually functionality to solve it automatically. Desktop-only.

## Plan

1. ~~Set up Svelte, Jest, Prettier~~
2. Create rudimentary page wherein to store game
3. Create Node class to store all data:
   - `isMine`: Boolean
   - `isFlagged`: Boolean
   - `isVisible`: Boolean
   - Either lots of neighbour properties in graph structure, e.g. `northeastNeighbour: <reference to other Node>` or simply an integer to store the number of mine neighbours, which is calculated before the game begins
   - `coordinates`: `{ x: Int, y: Int }` to show the position of the tiles on the board
   - Static property to store amount of mines correctly flagged
4. Find out standard board sizes and how many mines per board, then create multidimensional array of all Nodes
5. Set `x` amount of nodes to be bombs in random locations
6. Populate `neighbour` field(s)
7. Create function to draw HTML canvas (named something like `renderBoard()`), with grid-style layout, using the array to define what to show and how to show it (e.g. flagged fields and such)
8. Create `onClick` method to set clicked node to visible. Then, if it's a bomb, end the game (needs a further method to do).
   - Need to figure out how to do the logic for large areas where none of the nodes have any mines as neighbours
   - Perhaps a Boolean field on the Node object to indicate whether any given node has neighbours who neighbour 0 bombs.
9. Create a right-click method to apply a flag to a field
10. Add things like a a bomb counter showing the amount of flags put onto the game, and the ability to change the board's size. Plus potentially a ticking time counter, for authenticity

---

# This repo is no longer maintained. Consider using `npm init vite` and selecting the `svelte` option or — if you want a full-fledged app framework — use [SvelteKit](https://kit.svelte.dev), the official application framework for Svelte

---

# svelte app

This is a project template for [Svelte](https://svelte.dev) apps. It lives at <https://github.com/sveltejs/template>.

To create a new project based on this template using [degit](https://github.com/Rich-Harris/degit):

```bash
npx degit sveltejs/template svelte-app
cd svelte-app
```

*Note that you will need to have [Node.js](https://nodejs.org) installed.*

## Get started

Install the dependencies...

```bash
cd svelte-app
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

Navigate to [localhost:8080](http://localhost:8080). You should see your app running. Edit a component file in `src`, save it, and reload the page to see your changes.

By default, the server will only respond to requests from localhost. To allow connections from other computers, edit the `sirv` commands in package.json to include the option `--host 0.0.0.0`.

If you're using [Visual Studio Code](https://code.visualstudio.com/) we recommend installing the official extension [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode). If you are using other editors you may need to install a plugin in order to get syntax highlighting and intellisense.

## Building and running in production mode

To create an optimised version of the app:

```bash
npm run build
```

You can run the newly built app with `npm run start`. This uses [sirv](https://github.com/lukeed/sirv), which is included in your package.json's `dependencies` so that the app will work when you deploy to platforms like [Heroku](https://heroku.com).

## Single-page app mode

By default, sirv will only respond to requests that match files in `public`. This is to maximise compatibility with static fileservers, allowing you to deploy your app anywhere.

If you're building a single-page app (SPA) with multiple routes, sirv needs to be able to respond to requests for *any* path. You can make it so by editing the `"start"` command in package.json:

```js
"start": "sirv public --single"
```

## Using TypeScript

This template comes with a script to set up a TypeScript development environment, you can run it immediately after cloning the template with:

```bash
node scripts/setupTypeScript.js
```

Or remove the script via:

```bash
rm scripts/setupTypeScript.js
```

If you want to use `baseUrl` or `path` aliases within your `tsconfig`, you need to set up `@rollup/plugin-alias` to tell Rollup to resolve the aliases. For more info, see [this StackOverflow question](https://stackoverflow.com/questions/63427935/setup-tsconfig-path-in-svelte).

## Deploying to the web

### With [Vercel](https://vercel.com)

Install `vercel` if you haven't already:

```bash
npm install -g vercel
```

Then, from within your project folder:

```bash
cd public
vercel deploy --name my-project
```

### With [surge](https://surge.sh/)

Install `surge` if you haven't already:

```bash
npm install -g surge
```

Then, from within your project folder:

```bash
npm run build
surge public my-project.surge.sh
```
