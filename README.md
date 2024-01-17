# Testing the GOSH FHIR API

Kindly be aware that the API in use is an Azure FHIR API, and for the purposes of the Hack, synthetic FHIR data has been loaded into it.

This application essentially calculates the occurrence count of specified conditions within a chosen year.

## Project setup

Retrieve the application by downloading it. Once you're in the root directory, generate a file named `.env` and insert your `token` in the format `VITE_TOKEN="add-token-here"`. Afterward, execute the application.

```
# yarn
yarn

# npm
npm install

# pnpm
pnpm install

# pnpm
bun install
```

### Compiles and hot-reloads for development

```
# yarn
yarn dev

# npm
npm run dev

To compile and hot-reload on a specified port (example 8006), run

```bash
npm run dev -- --port 8006
``` 

# pnpm
pnpm dev

# bun
bun run dev
```

### Compiles and minifies for production

```
# yarn
yarn build

# npm
npm run build

# pnpm
pnpm build

# bun
bun run build
```

### Lints and fixes files

```
# yarn
yarn lint

# npm
npm run lint

# pnpm
pnpm lint

# bun
bun run lint
```

### Customize configuration

See [Configuration Reference](https://vitejs.dev/config/).
