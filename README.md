<div align="center"> <a href="https://fastify.dev/">
    <img
      src="https://github.com/fastify/graphics/raw/HEAD/fastify-landscape-outlined.svg"
      width="650"
      height="auto"
    />
  </a>
</div>

<div align="center">

[![CI](https://github.com/fastify/fastify/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/ci.yml)
[![Package Manager
CI](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml)
[![Web
site](https://github.com/fastify/fastify/actions/workflows/website.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/website.yml)
[![neostandard javascript style](https://img.shields.io/badge/code_style-neostandard-brightgreen?style=flat)](https://github.com/neostandard/neostandard)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/7585/badge)](https://bestpractices.coreinfrastructure.org/projects/7585)

</div>

<div align="center">

[![NPM
version](https://img.shields.io/npm/v/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![NPM
downloads](https://img.shields.io/npm/dm/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![Security Responsible
Disclosure](https://img.shields.io/badge/Security-Responsible%20Disclosure-yellow.svg)](https://github.com/fastify/fastify/blob/main/SECURITY.md)
[![Discord](https://img.shields.io/discord/725613461949906985)](https://discord.gg/fastify)
[![Contribute with Gitpod](https://img.shields.io/badge/Contribute%20with-Gitpod-908a85?logo=gitpod&color=blue)](https://gitpod.io/#https://github.com/fastify/fastify)
![Open Collective backers and sponsors](https://img.shields.io/opencollective/all/fastify)

</div>

<br />

# TL;DR

* [Fastify](https://github.com/fastify/fastify) is a fast and low overhead web framework for Node.js.
* This package shows how fast it is compared to other JS frameworks: these benchmarks do not pretend to represent a real-world scenario, but they give a **good indication of the framework overhead**.
* The benchmarks are run automatically on GitHub actions, which means they run on virtual hardware that can suffer from the "noisy neighbor" effect; this means that the results can vary.
* For metrics (cold-start) see [metrics.md](./METRICS.md)

# Requirements

To be included in this list, the framework should captivate users' interest. We have identified the following minimal requirements:
- **Ensure active usage**: a minimum of 500 downloads per week
- **Maintain an active repository** with at least one event (comment, issue, PR) in the last month
- The framework must use the **Node.js** HTTP module

# Usage

Clone this repo. Then

```
node ./benchmark [arguments (optional)]
```

#### Arguments

* `-h`: Help on how to use the tool.
* `bench`:  Benchmark one or more modules.
* `compare`: Get comparative data for your benchmarks.

> Create benchmark before comparing; `benchmark bench`

> You may also compare all test results, at once, in a single table; `benchmark compare -t`

> You can also extend the comparison table with percentage values based on fastest result; `benchmark compare -p`
# Benchmarks

* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v24.21.0`
* __Run:__ Thu Oct 01 2026 05:09:33 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 55284.8    | 17.57        | 9.86          |
| restana                  | v5.2.0   | ✓      | 54848.0    | 17.76        | 9.78          |
| fastify                  | 5.12.5   | ✓      | 51551.2    | 18.93        | 9.24          |
| h3                       | 1.15.11  | ✗      | 50885.6    | 19.17        | 9.07          |
| h3-router                | 1.15.11  | ✓      | 50842.4    | 19.14        | 9.07          |
| micro                    | 10.0.1   | ✗      | 49559.2    | 19.65        | 8.84          |
| node-http                | v24.21.0 | ✗      | 49485.6    | 19.66        | 8.82          |
| polka                    | 0.5.2    | ✓      | 49013.6    | 19.94        | 8.74          |
| connect                  | 3.7.0    | ✗      | 47995.2    | 20.39        | 8.56          |
| connect-router           | 2.2.0    | ✓      | 44088.0    | 22.24        | 7.86          |
| hono                     | 4.13.12  | ✓      | 42181.6    | 23.19        | 6.92          |
| koa                      | 3.2.1    | ✗      | 38905.0    | 25.19        | 6.94          |
| whatwg-node-server       | 0.10.18  | ✗      | 37065.8    | 26.46        | 6.61          |
| koa-router               | 14.0.0   | ✓      | 36514.4    | 26.89        | 6.51          |
| adonisjs                 | 7.8.1    | ✓      | 36209.8    | 27.10        | 6.46          |
| hapi                     | 21.4.10  | ✓      | 32369.8    | 30.42        | 5.77          |
| express                  | 5.2.1    | ✓      | 28109.2    | 35.07        | 5.01          |
| srvx                     | 0.10.1   | ✗      | 27044.0    | 36.47        | 5.26          |
| microrouter              | 3.1.3    | ✓      | 26148.8    | 37.73        | 4.66          |
| express-with-middlewares | 5.2.1    | ✓      | 23265.2    | 42.47        | 8.65          |
| fastify-big-json         | 5.12.5   | ✓      | 14224.2    | 69.77        | 163.66        |
| trpc-router              | 11.19.0  | ✓      | 10372.0    | 95.80        | 2.36          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
