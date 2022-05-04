# Tezos Domains GQL client

[![npm version](https://badge.fury.io/js/%40dipdup%2Fdomains.svg)](https://badge.fury.io/js/%40dipdup%2Fdomains)
[![Made With](https://img.shields.io/badge/made%20with-dipdup-blue.svg?)](https://dipdup.net)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Autogenerated Tezos Domains fully typed SDK with a built-in GQL client.

## Installation

```
npm i @dipdup/domains
```

## Usage

First of all you need to create an instance of domains client:
```js
import { createClient } from '@dipdup/domains'

const client = createClient({
    url: 'http://domains.dipdup.net/v1/graphql',
    subscription: {
        url: "wss://domains.dipdup.net/v1/graphql"
    }
});
```

#### Query

```js
import { everything } from '@dipdup/domains'

client.chain.query
    .record({
        where: { 
            address: { _eq: 'KT1P8n2qzJjwMPbHJfi4o8xu6Pe3gaU3u2A3' }
        }
    })
    .get({ ...everything })
    .then(res => console.log)
```