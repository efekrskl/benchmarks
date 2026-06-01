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
* __Node:__ `v24.16.0`
* __Run:__ Mon Jun 01 2026 01:33:35 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 59822.4    | 16.22        | 10.67         |
| restana                  | v5.2.0   | ✓      | 57623.2    | 16.90        | 10.28         |
| node-http                | v24.16.0 | ✗      | 56799.2    | 17.08        | 10.13         |
| polka                    | 0.5.2    | ✓      | 55807.2    | 17.41        | 9.95          |
| h3-router                | 1.15.11  | ✓      | 55710.4    | 17.45        | 9.94          |
| connect                  | 3.7.0    | ✗      | 55218.4    | 17.58        | 9.85          |
| h3                       | 1.15.11  | ✗      | 54786.4    | 17.76        | 9.77          |
| fastify                  | 5.8.5    | ✓      | 53497.6    | 18.24        | 9.59          |
| micro                    | 10.0.1   | ✗      | 53158.4    | 18.32        | 9.48          |
| connect-router           | 2.2.0    | ✓      | 51661.6    | 18.86        | 9.21          |
| whatwg-node-server       | 0.10.18  | ✗      | 50168.8    | 19.43        | 8.95          |
| hono                     | 4.12.23  | ✓      | 45800.8    | 21.33        | 7.51          |
| koa                      | 3.2.1    | ✗      | 44048.0    | 22.20        | 7.86          |
| koa-router               | 14.0.0   | ✓      | 41553.6    | 23.57        | 7.41          |
| hapi                     | 21.4.9   | ✓      | 39756.0    | 24.66        | 7.09          |
| adonisjs                 | 7.8.1    | ✓      | 38616.8    | 25.41        | 6.89          |
| srvx                     | 0.10.1   | ✗      | 34842.0    | 28.21        | 6.78          |
| express                  | 5.2.1    | ✓      | 34541.0    | 28.47        | 6.16          |
| microrouter              | 3.1.3    | ✓      | 33151.2    | 29.66        | 5.91          |
| express-with-middlewares | 5.2.1    | ✓      | 29221.2    | 33.73        | 10.87         |
| fastify-big-json         | 5.8.5    | ✓      | 14680.4    | 67.61        | 168.92        |
| trpc-router              | 11.17.0  | ✓      | 11323.4    | 87.75        | 2.58          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
