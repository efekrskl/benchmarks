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
* __Node:__ `v24.14.0`
* __Run:__ Sun Mar 01 2026 01:08:52 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| h3                       | 1.15.5   | ✗      | 53538.4    | 18.18        | 9.55          |
| 0http                    | 4.4.0    | ✓      | 53411.2    | 18.23        | 9.53          |
| node-http                | v24.14.0 | ✗      | 47804.8    | 20.46        | 8.53          |
| micro                    | 10.0.1   | ✗      | 47028.8    | 20.77        | 8.39          |
| restana                  | v5.1.0   | ✓      | 46912.0    | 20.81        | 8.37          |
| fastify                  | 5.7.4    | ✓      | 46339.2    | 21.06        | 8.31          |
| h3-router                | 1.15.5   | ✓      | 46005.6    | 21.25        | 8.20          |
| polka                    | 0.5.2    | ✓      | 45934.4    | 21.26        | 8.19          |
| connect                  | 3.7.0    | ✗      | 45727.2    | 21.36        | 8.15          |
| connect-router           | 2.2.0    | ✓      | 42977.6    | 22.76        | 7.66          |
| whatwg-node-server       | 0.10.18  | ✗      | 40305.6    | 24.32        | 7.19          |
| hono                     | 4.12.3   | ✓      | 37253.6    | 26.36        | 6.11          |
| koa                      | 3.1.2    | ✗      | 36512.6    | 26.91        | 6.51          |
| koa-router               | 14.0.0   | ✓      | 34844.0    | 28.20        | 6.21          |
| adonisjs                 | 7.8.0    | ✓      | 34768.2    | 28.28        | 6.20          |
| hapi                     | 21.4.6   | ✓      | 33951.6    | 28.94        | 6.05          |
| srvx                     | 0.10.1   | ✗      | 28159.6    | 35.01        | 5.48          |
| express                  | 5.2.1    | ✓      | 26983.2    | 36.55        | 4.81          |
| microrouter              | 3.1.3    | ✓      | 25697.6    | 38.41        | 4.58          |
| express-with-middlewares | 5.2.1    | ✓      | 22349.6    | 44.23        | 8.31          |
| fastify-big-json         | 5.7.4    | ✓      | 13208.8    | 75.18        | 151.98        |
| trpc-router              | 11.10.0  | ✓      | 9618.5     | 103.33       | 2.12          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
