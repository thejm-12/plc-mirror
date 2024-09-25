# PLC mirror

Syncs PLC operations log into a local table, and allows resolving `did:plc:`
DIDs without putting strain on https://plc.directory and hitting rate limits.

## Setup

* Decide where do you want to store the data
* Copy `example.env` to `.env` and edit it to your liking.
    * `POSTGRES_PASSWORD` can be anything, it will be used on the first start of
      `postgres` container to initialize the database.
* `make up`

## Usage

You can directly replace `https://plc.directory` with a URL to the exposed port
(11004 by default).

Note that on the first run it will take quite a few hours to download everything,
and the mirror with respond with 500 if it's not caught up yet.
