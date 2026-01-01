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
* __Node:__ `v24.12.0`
* __Run:__ Thu Jan 01 2026 20:51:34 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 54622.4    | 17.80        | 9.74          |
| h3                       | 1.15.4   | ✗      | 53204.0    | 18.30        | 9.49          |
| h3-router                | 1.15.4   | ✓      | 51768.8    | 18.84        | 9.23          |
| restana                  | v5.1.0   | ✓      | 51437.6    | 18.96        | 9.17          |
| node-http                | v24.12.0 | ✗      | 47768.0    | 20.46        | 8.52          |
| polka                    | 0.5.2    | ✓      | 46840.8    | 20.83        | 8.35          |
| connect                  | 3.7.0    | ✗      | 46493.6    | 21.02        | 8.29          |
| micro                    | 10.0.1   | ✗      | 46092.0    | 21.19        | 8.22          |
| fastify                  | 5.6.2    | ✓      | 45768.0    | 21.36        | 8.20          |
| connect-router           | 2.2.0    | ✓      | 43659.2    | 22.41        | 7.79          |
| whatwg-node-server       | 0.10.17  | ✗      | 40152.8    | 24.40        | 7.16          |
| koa                      | 3.1.1    | ✗      | 37593.6    | 26.13        | 6.70          |
| hono                     | 4.11.3   | ✓      | 37441.8    | 26.20        | 6.14          |
| koa-router               | 14.0.0   | ✓      | 35086.4    | 27.99        | 6.26          |
| hapi                     | 21.4.4   | ✓      | 33916.4    | 28.97        | 6.05          |
| adonisjs                 | 7.7.0    | ✓      | 31853.2    | 30.89        | 5.68          |
| srvx                     | 0.10.0   | ✗      | 29616.8    | 33.26        | 5.76          |
| express                  | 5.2.1    | ✓      | 27396.8    | 35.99        | 4.89          |
| express-with-middlewares | 5.2.1    | ✓      | 23636.8    | 41.78        | 8.79          |
| microrouter              | 3.1.3    | ✓      | 20238.4    | 48.89        | 3.61          |
| fastify-big-json         | 5.6.2    | ✓      | 12565.4    | 79.03        | 144.55        |
| trpc-router              | 11.8.1   | ✓      | 8756.0     | 113.59       | 1.93          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
