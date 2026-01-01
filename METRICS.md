# Metrics
* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v24.12.0`
* __Run:__ Thu Jan 01 2026 20:21:51 GMT+0000 (Coordinated Universal Time)
* __Method:__ `npm run metrics` (samples: 5)
* __startup:__ time elapsed to setup the application
* __listen:__ time elapsed until the http server is ready to accept requests (cold start)

| | startup(ms) | listen(ms) |
|-| -       | -      |
| 1-startup-routes-schema.cjs | 91.35 | 122.74 |
| 1-startup-routes.cjs | 92.12 | 102.30 |
| 10-startup-routes-schema.cjs | 92.80 | 125.08 |
| 10-startup-routes.cjs | 93.64 | 105.25 |
| 100-startup-routes-schema.cjs | 99.58 | 135.72 |
| 100-startup-routes.cjs | 100.64 | 121.48 |
| 1000-startup-routes-schema.cjs | 185.93 | 247.50 |
| 1000-startup-routes.cjs | 189.04 | 249.86 |
| 10000-startup-routes-schema.cjs | 3642.02 | 3890.57 |
| 10000-startup-routes.cjs | 3157.12 | 4574.28 |
| startup-listen.cjs | 106.77 | 120.26 |
