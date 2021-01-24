<div align=center>
    <img src="https://raw.githubusercontent.com/BoatSpace/boatspace.js/main/images/boat_circle.png">
    <p> 
        <a href="https://discord.gg/6rU4rVZ">
            <img src="https://img.shields.io/discord/609125459690651649?color=7289da&logo=discord&logoColor=white" alt="Discord">
        </a>
        <a href="https://www.npmjs.com/package/boatspace.js">
            <img src="https://img.shields.io/npm/v/webhooks.js.svg" alt="npm">
        </a>
        <a href="https://www.npmjs.com/package/boatspace.js">
            <img src="https://img.shields.io/npm/dt/boatspace.js.svg?maxAge=3600" alt="NPM downloads">
        </a>
    </p>
    <p>
        <a href="https://nodei.co/npm/boatspace.js/"><img src="https://nodei.co/npm/boatspace.js.png?downloads=true&stars=true" alt="npm installnfo" /></a>
    </p>
</div>

## Table of Contents
- [About](#about)
- [Installation](#installation)
- [Example](#example)

## About
boatspace.js is the official Node.js wrapper for the BoatSpace API.

## Installation
`npm i -s boatspace.js`

## Example
```js

const discord = require('discord.js')

const boatspace = require('boatspace.js')
const client = new discord.Client() // a discord client

client.on('ready', () => {
  // init boatspace
  boatspace.init({ key: "your-bots-api-key-here" })

  boatspace.postStats({ server_count: client.guilds.cache.size })
  .then(() => {
      console.log("POSTed bot stats to BoatSpace")
  })
  .catch(err => {
      console.error(err)
  })
})