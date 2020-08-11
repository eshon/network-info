# Filecoin Network Information

This repo contains information about all the active Filecoin networks. To follow steps to connect to a Filecoin network, please visit [Connect to a network](https://docs.filecoin.io/how-to/networks/) on the Filecoin Documentation site. The information in this repo will soon be automatically rendered onto a separate website or the Filecoin Documentation site.

## Current Active Networks and Usage Information

See [this page](https://docs.filecoin.io/how-to/networks/) on the Filecoin Documentation Site.

## Network Information Data Model

For each Filecoin network, we include the following information:
- Network name
- Network status:
  - 🔴 Network down for all participants
  - 🟡 Network is unstable (down for some participants, but not all)
  - 🟢 Network up and stable
- Link to the genesis CAR files for the network
- Link to the faucet for the network (if the network is not `mainnet`)
- Supported sector sizes on this network
- The minimum miner power required to participate in Filecoin consensus on this network
- Chain genesis information, including when this network was last reset and the hash of the genesis block
- Addresses for the bootstrap peers on this network

Information for each network is stored in a JSON file. Currently information for each network can be found on the [this page](https://docs.filecoin.io/how-to/networks/) on the Filecoin Documentation Site, or on the respective information page for each network:
- `nerpa` network: https://www.nerpa.fildev.network/
- `butterfly` network: https://www.butterfly.fildev.network/
- `calibration` network: https://www.calibration.fildev.network/

## Build & Deploy

This application builds a static site using Nuxt.js/Vue.js. The site is generated to the `/dist/` directory during the build process. Only this directory needs to be published.

### Nuxt settings
- Remove `mode` property from `nuxt.config.js`
- Set `target: 'static'` in `nuxt.config.js`

### Fleek configuration
- A `.fleek.json` configuration file is included which should pre-populate these settings
- Build command: `npm ci && npm run generate`
- Base directory can be left empty
- Publish directory: `dist`
- Environment variables:
  - NODE_ENV=production

### Deployment process
- Commit to a repo on GitHub
- Login to Fleek, click on "Hosting" and click on "Add new site"
- Connect your GitHub repo
- The remaining information should populate automatically, however, if it doesn't:
 - Select NuxtJS as the framework
 - Input the settings as defined in `#fleek-settings`
- Select "Deploy Site"
- 🎉
