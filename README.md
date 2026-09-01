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
* __Node:__ `v24.20.0`
* __Run:__ Tue Sep 01 2026 04:30:58 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 50963.2    | 19.13        | 9.09          |
| h3                       | 1.15.11  | ✗      | 50426.4    | 19.30        | 8.99          |
| restana                  | v5.2.0   | ✓      | 48824.8    | 19.99        | 8.71          |
| h3-router                | 1.15.11  | ✓      | 47597.6    | 20.51        | 8.49          |
| fastify                  | 5.12.1   | ✓      | 46340.8    | 21.05        | 8.31          |
| connect                  | 3.7.0    | ✗      | 42329.6    | 23.11        | 7.55          |
| node-http                | v24.20.0 | ✗      | 42122.4    | 23.26        | 7.51          |
| polka                    | 0.5.2    | ✓      | 41895.2    | 23.36        | 7.47          |
| micro                    | 10.0.1   | ✗      | 41498.4    | 23.62        | 7.40          |
| connect-router           | 2.2.0    | ✓      | 38677.0    | 25.35        | 6.90          |
| hono                     | 4.13.5   | ✓      | 36227.4    | 27.09        | 5.94          |
| whatwg-node-server       | 0.10.18  | ✗      | 35906.2    | 27.33        | 6.40          |
| koa                      | 3.2.1    | ✗      | 35068.0    | 28.03        | 6.25          |
| koa-router               | 14.0.0   | ✓      | 33066.2    | 29.73        | 5.90          |
| adonisjs                 | 7.8.1    | ✓      | 32351.6    | 30.40        | 5.77          |
| hapi                     | 21.4.10  | ✓      | 31989.4    | 30.76        | 5.70          |
| srvx                     | 0.10.1   | ✗      | 27078.8    | 36.42        | 5.27          |
| express                  | 5.2.1    | ✓      | 24889.2    | 39.66        | 4.44          |
| microrouter              | 3.1.3    | ✓      | 23228.8    | 42.53        | 4.14          |
| express-with-middlewares | 5.2.1    | ✓      | 21656.4    | 45.67        | 8.05          |
| fastify-big-json         | 5.12.1   | ✓      | 13976.6    | 71.00        | 160.81        |
| trpc-router              | 11.18.0  | ✓      | 10123.5    | 98.19        | 2.31          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
