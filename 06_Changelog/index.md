# Changelog 🗒️

This document describes project changes.

Table of contents:

- [Changelog 🗒️](#changelog-%f0%9f%97%92%ef%b8%8f)
  - [v2](#v2)
    - [2.1.0](#210)
      - [2.1.3](#213)
      - [2.1.2](#212)
      - [2.1.1](#211)
    - [2.0.1](#201)
  - [v1](#v1)
    - [1.6.0](#160)
    - [1.5.0](#150)
    - [1.4.0](#140)
      - [1.4.1](#141)
    - [1.3.0](#130)
    - [1.2.0](#120)
    - [1.1.0](#110)

## v2

Second version of prototype defines Non-semester state for Students and Teachers

### 2.1.0

- Logger system creation
- Tests written

#### 2.1.3

- Dependencies update
  - helmet: 3.21.3 -> 3.22.0
  - mocha: 7.1.0 -> 7.1.1
  - babel-plugin-root-import: 6.4.1 -> 6.5.0
  - @babel/core: 7.8.4 -> 7.9.0
  - @babel/preset-env: 7.8.4 -> 7.9.5

#### 2.1.2

- Minor logger updates
- Services bug fix

#### 2.1.1

- Configs are changed
- Pipe listening to events
- Event cleaning

### 2.0.1

- system::setup event changed to server::setup
- Testing process added to scripts

## v1

First version contains basis of all the system. With database system, event-pipe system, collectors and services all these could be easily maintained and scaled.

### 1.6.0

- UsersService defined
- Models implemented
- .rest files accepted as test files

### 1.5.0

- Database integration
- Event-pipe implemented
- Production routes set

### 1.4.0

- Improved documentation
- Restructuring back-end

#### 1.4.1

- Fixes JWT

### 1.3.0

- Restructuring front-end
- Added internalization
- Back-end: refactoring route collector
- Back-end: adding JWT service

### 1.2.0

- Babel configured
- Babel import root module added
- vue-cookies added
- token check implemented

### 1.1.0

- Project defined
