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
* __Node:__ `v24.18.1`
* __Run:__ Sat Aug 01 2026 01:12:58 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 55663.2    | 17.44        | 9.93          |
| restana                  | v5.2.0   | ✓      | 54543.2    | 17.83        | 9.73          |
| h3                       | 1.15.11  | ✗      | 53255.2    | 18.27        | 9.50          |
| h3-router                | 1.15.11  | ✓      | 52694.4    | 18.48        | 9.40          |
| node-http                | v24.18.1 | ✗      | 47272.8    | 20.66        | 8.43          |
| fastify                  | 5.11.0   | ✓      | 46699.2    | 20.88        | 8.37          |
| micro                    | 10.0.1   | ✗      | 46644.8    | 20.93        | 8.32          |
| connect                  | 3.7.0    | ✗      | 45922.4    | 21.27        | 8.19          |
| polka                    | 0.5.2    | ✓      | 45404.8    | 21.51        | 8.10          |
| connect-router           | 2.2.0    | ✓      | 43280.0    | 22.58        | 7.72          |
| whatwg-node-server       | 0.10.18  | ✗      | 39616.2    | 24.74        | 7.06          |
| hono                     | 4.12.33  | ✓      | 36524.0    | 26.89        | 5.99          |
| koa                      | 3.2.1    | ✗      | 35702.2    | 27.54        | 6.37          |
| hapi                     | 21.4.10  | ✓      | 34449.6    | 28.53        | 6.14          |
| koa-router               | 14.0.0   | ✓      | 33875.4    | 29.03        | 6.04          |
| adonisjs                 | 7.8.1    | ✓      | 33866.4    | 29.02        | 6.04          |
| express                  | 5.2.1    | ✓      | 27545.2    | 35.80        | 4.91          |
| srvx                     | 0.10.1   | ✗      | 26725.6    | 36.91        | 5.20          |
| microrouter              | 3.1.3    | ✓      | 25143.2    | 39.27        | 4.48          |
| express-with-middlewares | 5.2.1    | ✓      | 23048.8    | 42.87        | 8.57          |
| fastify-big-json         | 5.11.0   | ✓      | 14263.4    | 69.56        | 164.12        |
| trpc-router              | 11.18.0  | ✓      | 10025.6    | 99.14        | 2.28          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
