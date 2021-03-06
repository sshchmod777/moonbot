# MoonBot
## A (very) simple cryptocurrency trading bot.

_Hold on tight, folks. We're going to the moon!*_

![Boot Screen](docs/boot-screen.png)

**Please Note:** This is a work in progress.

This project is an attempt to build an automated bot for trading cryptocurrencies. Some ideas are based upon the work of others who've come before, notably [Zenbot](https://github.com/DeviaVir/zenbot) and [Gekko](https://github.com/askmike/gekko).

<sub>\*Most likely not going to the moon.</sub>

**IMPORTANT: In order to use LIVE trading, you will need to provide your Binance API key in `config.js`. Note that if you use enable live trading, you will MOST LIKELY / PROBABLY / DEFINITELY LOSE MONEY.**

## Installation & Usage

To get started, follow the steps below:

```
> git clone https://github.com/daveschumaker/moonbot.git
> cd moonbot
> cp config-sample.js config.js
> npm install
> ./moonbot.js
```

Optionally, you can also run `npm link` from the root folder of the _MoonBot_ project and it will be available as a global binary that you can run from anywhere on your system using `moonbot`.

_MoonBot_ will begin fetching real data from Binance and display the results in your terminal.

## Setup

Open `config.js` in the root project directory and enter your relevant configuration details (the Binance API key is optional at this time and will only used for fetching and placing orders with your personal account). You do not need it to run _MoonBot_ in its default simulation mode.

## How to run MoonBot

To get started with default options using the sample configuration file, simply start the project with `npm start`. Some additional tools are provided.

### Backfill older trade data.

```
moonbot backfill

  Usage: backfill [options]

  Add trade details for a particular symbol to database for use in sims and calculating longer period data.

  Options:

    --dateFrom <YYYYMMDD>   Required: Initial date to start fetching trade data from.
    --dateTo <YYYYMMDD>     Optional: Date to stop fetching trade data. Defaults to current date.
    --symbol <name>         Optional: Market symbol for trade data to fetch. Defaults to config.js.

  Example:

    moonbot backfill --dateFrom 20180101 --symbol NEOETH
```

### Simulate trade strategy

[WORK IN PROGRESS] Iterate through backfilled data for a certain period of time and simulate placing buy / sell orders based on a trading strategy that you provide.

```
moonbot sim

  Usage: sim [options]

  Add trade details for a particular symbol to database for use in sims and calculating longer period data.

  Options:

    --dateFrom <YYYYMMDD>   Required: Initial date to start simulation from.
    --dateTo <YYYYMMDD>     Required: Date to stop simulated.
    --symbol <name>         Optional: Market symbol used for simulation. Defaults to config.js.

  Example:

    moonbot sim --dateFrom 20180101 --dateTo 20180107 --symbol NEOETH
```

## To do

There are a number of things still to implement and cleanup. A small sample of ideas can be found inside [TODOs.md](TODOs.md)