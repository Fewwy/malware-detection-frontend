[![Build Status](https://travis-ci.org/RedHatInsights/malware-detection-frontend.svg?branch=master)](https://travis-ci.org/RedHatInsights/malware-detection-frontend)

# malware-detection-frontend

Malware Detection for Red Hat Insights products that includes Patternfly 4 and shared cloud.redhat.com utilities.

## Getting Started

There is a [comprehensive quick start guide in the Storybook Documentation](https://github.com/RedHatInsights/insights-frontend-storybook/blob/master/src/docs/welcome/quickStart/DOC.md) to setting up an Insights environment complete with:

- [Insights Chroming](https://github.com/RedHatInsights/insights-chrome)
- [Insights Proxy](https://github.com/RedHatInsights/insights-proxy)

Note: You will need to set up the Insights environment if you want to develop with the malware-detection-frontend app due to the consumption of the chroming service as well as setting up your global/app navigation through the API.

## Build app

1. ```npm install```

2. ```npm run start```
    - starts webpack bundler and serves the files with webpack dev server

    OR 

2. ```npm run start:proxy```
  - starts webpack bundler and serves the files with webpack dev server and runs chrome proxy (prod env) (one less terminal required)

3. visit ```https://prod.foo.redhat.com:1337/insights/malware/```

### Testing

- `npm run verify` will run linters and tests
- Travis is used to test the build for this code.
  - You are always notified on failed builds
  - You are only notified on successful builds if the build before it failed
  - By default, both `push` events as well as `pull_request` events send notifications
  - Travis is defaulted to notify #insights-bots
## Deploying

- The Platform team is using Travis to deploy the application
  - The Platform team will help you set up the Travis instance if this is the route you are wanting to take

## Running locally
Have [insights-proxy](https://github.com/RedHatInsights/insights-proxy) installed under PROXY_PATH  (only necessary if your not using start:proxy)

```shell
SPANDX_CONFIG="./profiles/local-frontend.js" bash $PROXY_PATH/scripts/run.sh
```

Have [yara-backend](https://github.com/RedHatInsights/yara-backend) installed and run ```docker-compose up```

