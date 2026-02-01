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
* __Node:__ `v24.13.0`
* __Run:__ Sun Feb 01 2026 01:09:49 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| h3-router                | 1.15.5   | ✓      | 53844.8    | 18.09        | 9.60          |
| restana                  | v5.1.0   | ✓      | 53469.6    | 18.20        | 9.54          |
| h3                       | 1.15.5   | ✗      | 51504.0    | 18.90        | 9.18          |
| 0http                    | 4.4.0    | ✓      | 49217.6    | 19.82        | 8.78          |
| polka                    | 0.5.2    | ✓      | 47105.6    | 20.73        | 8.40          |
| node-http                | v24.13.0 | ✗      | 46941.6    | 20.81        | 8.37          |
| micro                    | 10.0.1   | ✗      | 46432.8    | 21.04        | 8.28          |
| connect                  | 3.7.0    | ✗      | 46260.8    | 21.12        | 8.25          |
| fastify                  | 5.7.2    | ✓      | 45084.0    | 21.68        | 8.08          |
| connect-router           | 2.2.0    | ✓      | 43159.2    | 22.63        | 7.70          |
| whatwg-node-server       | 0.10.18  | ✗      | 39960.8    | 24.53        | 7.13          |
| hono                     | 4.11.7   | ✓      | 37303.2    | 26.31        | 6.12          |
| koa                      | 3.1.1    | ✗      | 36917.6    | 26.59        | 6.58          |
| koa-router               | 14.0.0   | ✓      | 34884.2    | 28.14        | 6.22          |
| hapi                     | 21.4.4   | ✓      | 33565.2    | 29.30        | 5.99          |
| adonisjs                 | 7.8.0    | ✓      | 32092.2    | 30.66        | 5.72          |
| srvx                     | 0.10.1   | ✗      | 29326.8    | 33.59        | 5.70          |
| express                  | 5.2.1    | ✓      | 27847.6    | 35.41        | 4.97          |
| express-with-middlewares | 5.2.1    | ✓      | 23292.0    | 42.42        | 8.66          |
| microrouter              | 3.1.3    | ✓      | 20906.0    | 47.32        | 3.73          |
| fastify-big-json         | 5.7.2    | ✓      | 12461.2    | 79.69        | 143.37        |
| trpc-router              | 11.9.0   | ✓      | 9473.1     | 104.94       | 2.09          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
