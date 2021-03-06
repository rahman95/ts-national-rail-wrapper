# TS National Rail Wrapper

[![npm version](https://badgen.net/npm/v/ts-national-rail-wrapper)](https://www.npmjs.org/package/ts-national-rail-wrapper)
[![npm downloads](https://badgen.net/npm/dw/ts-national-rail-wrapper)](http://npm-stat.com/charts.html?package=ts-national-rail-wrapper)
[![types included](https://badgen.net/npm/types/ts-national-rail-wrapper)](https://www.npmjs.org/package/ts-national-rail-wrapper)
[![publish size](https://badgen.net/packagephobia/publish/ts-national-rail-wrapper)](https://packagephobia.now.sh/result?p=ts-national-rail-wrapper)

✨Typescript promise based wrapper for National Rail SOAP API.

*Based on API docs found [here](https://lite.realtime.nationalrail.co.uk/OpenLDBWS/)*

## Prerequisite

- Yarn 🧶

## Usage

- Apply for an `API_KEY` to be used with the API from [National Rail](http://realtime.nationalrail.co.uk/OpenLDBWSRegistration/)
- Require package using Yarn
- Use it 🚀

Yarn:
```
yarn add ts-national-rail-wrapper
```

Example Usage:
```js
const { NationalRailWrapper } = require("ts-national-rail-wrapper")

const apiKey = "****-****-****-****"
const nationalRail = new NationalRailWrapper(apiKey)

...

const results = await nationalRail.getDepartures({ fromStation: "LDS", count: 5 })
```

## Methods

### getDepartures - Retrieve Departures for Station

```js
const options = { fromStation: "LDS", count: 5 }
const results = await nationalRail.getDepartures(options)
```

### getArrivals - Retrieve Arrivals for Station

```js
const options = { fromStation: "LDS", count: 5 }
const results = await nationalRail.getArrivals(options)
```

### getAll - Retrieve Both Departures and Arrivals for Station

```js
const options = { fromStation: "LDS", count: 10 }
const results = await nationalRail.getAll(options)
```

### getServiceDetails - Retrieve Details about a certain Rail Service

```js
const options = { serviceId: "RAIL_SERVICE_001" }
const results = await nationalRail.getServiceDetails(options)
```

## Tests 

Currently tests will use the actual National Rail API to make calls and test data returned, this works but can cause the tests to be flaky due to the ever changing nature of data.

In an ideal situation these API results should be mocked to have the same behaviour all the time, this is a possible improvement I could make.

Tests make use of the `dotenv` lib which will look for an apiKey set in the `.env` file, please make sure that exists before running test

Once thats all set up run `yarn test` to start test suite

 ---
 <p align="center">
    🚂🚃🚃🚃🚃🚃✨
 </p>