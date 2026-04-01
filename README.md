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
* __Node:__ `v24.14.1`
* __Run:__ Wed Apr 01 2026 01:13:29 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 51428.8    | 18.96        | 9.17          |
| h3-router                | 1.15.10  | ✓      | 50977.6    | 19.12        | 9.09          |
| node-http                | v24.14.1 | ✗      | 48956.0    | 19.92        | 8.73          |
| polka                    | 0.5.2    | ✓      | 47718.4    | 20.52        | 8.51          |
| connect                  | 3.7.0    | ✗      | 47491.2    | 20.53        | 8.47          |
| restana                  | v5.1.0   | ✓      | 47115.2    | 20.72        | 8.40          |
| fastify                  | 5.8.4    | ✓      | 47073.6    | 20.75        | 8.44          |
| micro                    | 10.0.1   | ✗      | 46988.8    | 20.79        | 8.38          |
| h3                       | 1.15.10  | ✗      | 45764.0    | 21.35        | 8.16          |
| connect-router           | 2.2.0    | ✓      | 44501.6    | 21.95        | 7.94          |
| whatwg-node-server       | 0.10.18  | ✗      | 41324.0    | 23.71        | 7.37          |
| hono                     | 4.12.9   | ✓      | 37180.0    | 26.40        | 6.10          |
| koa                      | 3.2.0    | ✗      | 36817.0    | 26.65        | 6.57          |
| adonisjs                 | 7.8.0    | ✓      | 36609.6    | 26.81        | 6.53          |
| koa-router               | 14.0.0   | ✓      | 34330.8    | 28.63        | 6.12          |
| hapi                     | 21.4.7   | ✓      | 33992.2    | 28.91        | 6.06          |
| srvx                     | 0.10.1   | ✗      | 28611.6    | 34.44        | 5.57          |
| express                  | 5.2.1    | ✓      | 27544.0    | 35.80        | 4.91          |
| microrouter              | 3.1.3    | ✓      | 26599.6    | 37.09        | 4.74          |
| express-with-middlewares | 5.2.1    | ✓      | 22986.4    | 42.99        | 8.55          |
| fastify-big-json         | 5.8.4    | ✓      | 13625.4    | 72.84        | 156.77        |
| trpc-router              | 11.16.0  | ✓      | 9534.0     | 104.29       | 2.17          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
