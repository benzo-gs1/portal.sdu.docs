# Loaders 🛫

This document describes loading process

Table of contents:

- [Loaders 🛫](#loaders-%f0%9f%9b%ab)
  - [Configs](#configs)
  - [Event Pipe](#event-pipe)
  - [Database](#database)
  - [Express](#express)
  - [Services](#services)
  - [Routes](#routes)

Loading main function asynchronously executes different parts of the system in order to start it.

Order of execution:

1. Configs
2. Pipe
3. [server::setup](../04_Pipe/Events.md#serversetup-event) event is fired
4. Database
5. Express
6. Services
7. Routes

## Configs

Configs function places configurations into a proper object. See [Configs](../02_Configs/index.md)

## Event Pipe

Event Pipe function initializes EventEmmiter2 object and starts to listen to all events fired at the system. See [Pipe](../04_Pipe/index.md)

## Database

Database function initializes MongoDB connection and returns it. See [Database](../../05_Database/index.md)

## Express

Express function initializes Express.app with middleware plugins. See [Plugins](../01_Plugins/index.md)

## Services

Services function collects all the services from the system. See [Services](../05_Services/index.md)

## Routes

Routes function collects all the api routes from the system and matches them with a proper folder given. In production, routes defined in test.js files are not being collected. See [Api](../../01_Rest_Api/index.md)
