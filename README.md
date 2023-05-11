# kcfgc-sync

A collection of utilites for pulling data out of start.gg and syncing it elsewhere.

## Setup

In the root of the repo:

```sh
npm i -g pnpm
pnpm i
```

## Development

Run to build everything in watch mode during development:

```sh
npm run watch
```

## CI/CD

To add a tournament to the automatically generated list of tournaments, add its slug to [auto.txt](./auto.txt).

## Packages

### [common](packages/common/)

Contains the shared schema describing a tournament.

### [start-gg](packages/start-gg/)

Utility for extracting tournament information from start.gg. Takes an `api-key` argument (can be omitted if the `START_GG_API_KEY` env variable is set), then a list of arguments that are the tournament slugs to extract. Writes to stdout.

```sh
node packages/start-gg/dist/index.js --api-key=mystartggapikey combo-breaker evo myothertournament
```
