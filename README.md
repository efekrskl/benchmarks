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
* __Node:__ `v24.15.0`
* __Run:__ Fri May 01 2026 01:23:53 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| restana                  | v5.2.0   | ✓      | 53144.0    | 18.30        | 9.48          |
| 0http                    | 4.4.0    | ✓      | 52408.8    | 18.60        | 9.35          |
| h3-router                | 1.15.11  | ✓      | 51536.0    | 18.91        | 9.19          |
| h3                       | 1.15.11  | ✗      | 51425.6    | 18.96        | 9.17          |
| node-http                | v24.15.0 | ✗      | 48492.0    | 20.13        | 8.65          |
| polka                    | 0.5.2    | ✓      | 47502.4    | 20.54        | 8.47          |
| micro                    | 10.0.1   | ✗      | 46559.2    | 21.00        | 8.30          |
| connect                  | 3.7.0    | ✗      | 45959.2    | 21.26        | 8.20          |
| fastify                  | 5.8.5    | ✓      | 45743.2    | 21.35        | 8.20          |
| connect-router           | 2.2.0    | ✓      | 43020.0    | 22.72        | 7.67          |
| whatwg-node-server       | 0.10.18  | ✗      | 40064.0    | 24.55        | 7.14          |
| hono                     | 4.12.16  | ✓      | 36626.6    | 26.83        | 6.01          |
| koa                      | 3.2.0    | ✗      | 35954.6    | 27.35        | 6.41          |
| hapi                     | 21.4.8   | ✓      | 34034.2    | 28.89        | 6.07          |
| koa-router               | 14.0.0   | ✓      | 33946.6    | 28.96        | 6.05          |
| adonisjs                 | 7.8.1    | ✓      | 33593.8    | 29.27        | 5.99          |
| srvx                     | 0.10.1   | ✗      | 27730.4    | 35.55        | 5.39          |
| express                  | 5.2.1    | ✓      | 27624.0    | 35.70        | 4.93          |
| microrouter              | 3.1.3    | ✓      | 25837.6    | 38.19        | 4.61          |
| express-with-middlewares | 5.2.1    | ✓      | 22691.2    | 43.56        | 8.44          |
| fastify-big-json         | 5.8.5    | ✓      | 13428.8    | 73.92        | 154.50        |
| trpc-router              | 11.17.0  | ✓      | 9365.3     | 106.16       | 2.13          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
