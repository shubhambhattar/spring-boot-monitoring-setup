This project aims to bootstart testing a spring-boot application in local environment by automatically setting up the following:
- cAdvisor (for container metrics)
- prometheus (for monitoring)
- Grafana (for visualization)
- spring-boot app

The spring-boot setup is mostly untouched (0 extra code apart from what comes by default from [https://start.spring.io](https://start.spring.io)) and includes the following dependencies:
- spring-boot-devtools
- spring-boot-configuration-processor
- lombok
- spring-boot-starter-actuator
- micrometer-registry-prometheus
- spring-boot-starter-web

Grafana will also contain a dashboard which has precreated graphs emitted by default from `micrometer` in the `spring-boot` app.
This will contain metrics related to:
- JVM:
    - **Memory**: Heap / NonHeap / Buffer <-> Used / Committed / Max
    - **GC**: Minor / Major GC Pauses with frequency
    - **Threads**: Thread States, Live, Daemon, Peak Threads
- Log Events - logback level frequencies    