# Testing the GOSH FHIR API

Kindly be aware that the API in use is an Azure FHIR API, and for the purposes of the Hack, [synthetic FHIR data](https://mitre.box.com/shared/static/ydmcj2kpwzoyt6zndx4yfz163hfvyhd0.zip) has been loaded into it using [FhirLoader](https://github.com/hansenms/FhirLoader) as recommended by Microsoft Azure for FHIR API developers.

This simple `smart-on-fhir application` essentially calculates the occurrence count of specified `Conditions` within a chosen `year`.

## Project setup

Retrieve the application by downloading it. Once you're in the root directory, generate a file named `.env` and insert your `token` in the format `VITE_TOKEN="add-token-here"`. Afterward, execute the application by running either of the following:

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
