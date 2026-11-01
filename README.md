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
* __Node:__ `v24.22.2`
* __Run:__ Sun Nov 01 2026 05:21:50 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| 0http                    | 4.4.0    | ✓      | 106787.2   | 9.00         | 19.04         |
| restana                  | v5.2.0   | ✓      | 105752.0   | 9.00         | 18.86         |
| node-http                | v24.22.2 | ✗      | 96569.6    | 9.85         | 17.22         |
| polka                    | 0.5.2    | ✓      | 93987.2    | 10.16        | 16.76         |
| h3                       | 1.15.11  | ✗      | 93707.2    | 10.19        | 16.71         |
| connect                  | 3.7.0    | ✗      | 91878.4    | 10.37        | 16.39         |
| micro                    | 10.0.1   | ✗      | 90718.4    | 10.53        | 16.18         |
| fastify                  | 5.12.7   | ✓      | 90296.0    | 10.58        | 16.19         |
| h3-router                | 1.15.11  | ✓      | 88241.6    | 10.82        | 15.74         |
| connect-router           | 2.2.0    | ✓      | 84297.6    | 11.43        | 15.03         |
| hono                     | 4.13.16  | ✓      | 80086.4    | 11.96        | 13.14         |
| koa                      | 3.2.1    | ✗      | 67824.4    | 14.21        | 12.10         |
| adonisjs                 | 7.8.1    | ✓      | 66717.2    | 14.44        | 11.90         |
| koa-router               | 14.0.0   | ✓      | 63940.4    | 15.16        | 11.40         |
| express                  | 5.3.0    | ✓      | 59255.2    | 16.39        | 10.57         |
| hapi                     | 21.4.12  | ✓      | 54813.6    | 17.74        | 9.78          |
| microrouter              | 3.1.3    | ✓      | 51483.2    | 18.92        | 9.18          |
| srvx                     | 0.10.1   | ✗      | 51480.0    | 18.93        | 10.02         |
| express-with-middlewares | 5.3.0    | ✓      | 47420.0    | 20.58        | 17.64         |
| fastify-big-json         | 5.12.7   | ✓      | 16967.6    | 58.39        | 195.22        |
| trpc-router              | 11.22.1  | ✓      | 16316.4    | 60.76        | 3.72          |
| restify                  | 11.1.0   | ✓      | N/A        | N/A          | N/A           |
| whatwg-node-server       | 0.10.18  | ✗      | N/A        | N/A          | N/A           |
