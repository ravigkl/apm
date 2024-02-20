# apm aka Application Performance Management or Application Performance Monitoring
## Telemetry Signals
There are 3 telemetry signals
- Logs - centralized for use patten analysis of users, apps and machines
- Metrics - error rates, app latencies
- Traces - identify root cause from distributed and connected systems

## Open source APM tools
- [Signoz](https://signoz.io/) : Highly [cheaper](https://signoz.io/blog/pricing-comparison-signoz-vs-datadog-vs-newrelic-vs-grafana/) than Datadog APM tool. It uses ClickHouse and powerful OLAP database.
- [Graphite](https://graphiteapp.org/): Graphite is an enterprise-ready monitoring tool that runs equally well on cheap hardware or Cloud infrastructure. Teams use Graphite to track the performance of their websites, applications, business services, and networked servers. It marked the start of a new generation of monitoring tools, making it easier than ever to store, retrieve, share, and visualize time-series data. It uses Whisper database, carbon for high performane services and graphite web for UI. UI of graphite is basic but you can integrate with Grafana for advance UI for APM.
- [PinPoint](https://pinpoint-apm.github.io/pinpoint/):  It is used  for transaction flow visiblity in Java/Python/PHP based applications. The database is Apache HBase, PinPoint-Collector as collector service, PinPoint-Web for UI Dashboard, PinPoint-Agent for application to be monitored. [Installation](https://pinpoint-apm.github.io/pinpoint/installation.html) guide. You should definitely check Pinpoint out If you want to
  - understand your application topology at a glance
  - monitor your application in Real-Time
  - gain code-level visibility to every transaction
  - install APM Agents without changing a single line of code
  - have minimal impact on the performance (approximately 3% increase in resource usage)
- [Prometheus](https://prometheus.io/): Prometheus enables you to capture time-series data as metrics. These metrics can be aggregated to give insights into the behavior of our systems. It designed for Single machine but can be extended by integrating with Grafana. It uses timeseries data as metrics.
- [JavaMelody](https://github.com/javamelody/javamelody): The goal of JavaMelody is to monitor Java or Java EE applications in QA and production environments. Used for Java/JEE based applications. 
- [Stagemonitor](https://www.stagemonitor.org/): Stagemonitor is an open source APM tool for Java server applications. It enables you to monitor the performance of your Java web app throughout its lifecycle in development, QA, and production. It monitors applications with the help of servlet filters and bytecode manipulation. It is good fit for non-web based java apps and legacy ejb as well.

Stagemonitor integrates well with time-series databases like ElasticSearch, Graphite, and InfluxDB to analyze graphed metrics and Kibana to analyze requests and call stacks.
- [Scouter](https://github.com/scouter-project/scouter): Scouter is an open source APM tool written in Java, Javascript, and Scala. It captures and shows metrics about users, services, and resources. Some of the key metrics that Scouter captures:

  1. Users - active users and recent users
  2. Services - Active service, TPS, Response time, Application profiles
  3. Resources - Cpu, Memory, Network and Heap usage, Connection pools, etc.
- [Zipkin](https://zipkin.io/): Zipkin is a distributed tracing system. It helps gather timing data needed to troubleshoot latency problems in service architectures. Features include both the collection and lookup of this data. Applications need to be “instrumented” to report trace data to Zipkin. This usually means configuration of a tracer or instrumentation library. The most popular ways to report data to Zipkin are via HTTP or Kafka, though many other options exist, such as Apache ActiveMQ, gRPC and RabbitMQ. The data served to the UI are stored in-memory, or persistently with a supported backend such as Apache Cassandra or Elasticsearch.
- [Jaeger](https://www.jaegertracing.io/): Jaeger is an open source APM tool developed at Uber, which was later donated to Cloud Native Computing Foundation(CNCF). Inspired by Google's Dapper, Jaeger is a distributed tracing system. It uses [OpenTelemetry](https://opentelemetry.io/). OpenTelemetry is a collection of APIs, SDKs, and tools. Use it to instrument, generate, collect, and export telemetry data (metrics, logs, and traces) to help you analyze your software’s performance and behavior.

Application that explains the use of Jaeger. [HotROD ride](https://github.com/jaegertracing/jaeger/tree/main/examples/hotrod) and [detailed demo](https://medium.com/opentracing/take-opentracing-for-a-hotrod-ride-f6e3141f7941)

It is used for monitoring and troubleshooting microservices-based distributed systems. Some of its key features include:

  - Distributed context propagation
  - Distributed transaction monitoring
  - Root cause analysis
  - Service dependency analysis
  - Performance / latency optimization
- [Apache Skywalking](https://skywalking.apache.org/): This open source APM tool is focused on monitoring distributed systems, including microservices, cloud-native, and container-based architectures. Some of the key features of the APM tool includes:

  - Service, service instance, endpoint metrics analysis
  - Root cause analysis with code profiling
  - Service topology map analysis
  - Slow services and endpoint detection
  - Distributed tracing and context propagation
Skywalking also supports the collection of telemetry data in multiple formats.


- [App Metrics](https://www.app-metrics.io/): App Metrics is an open-source and cross-platform .NET library used to record metrics within an application. App Metrics can run on .NET Core or on the full .NET framework also supporting .NET 4.5.2. App Metrics is an open source and cross-platform .NET library that can be used to capture application metrics within any .NET application. App Metrics provides extensions to report to various open source time-series databases. It also provides dashboards to visualize application metrics in real-time. Some of the key features of this open source APM tool includes:

  - Track metrics for any type of .NET applications
  - Measure the performance and error of each endpoint in an MVC or Web API project
  - Freedom to choose where to persist captured metrics and which dashboard tool to use for visualization
App Metrics does not include a visualization tool, but it does provide App Metrics specific Grafana dashboards.
- [Glowroot](https://glowroot.org/): The features of Glowroot APM are as follows.
  - Trace capture for slow requests and errors
  - Continuous profiling (with very handy filtering)
  - Response time breakdown charts
  - Response time percentile charts
  - SQL capture and aggregation
  - Service call capture and aggregation
  - MBean attribute capture and charts
  - Configurable alerting
  - Historical rollup of all data (1m, 5m, 30m, 4h) with configurable retention
  - Full support for async requests that span multiple threads
  - Responsive UI with mobile support
  Glowroot has been tested on the following application servers:
  -  Tomcat
  - TomEE
  - Wildfly
  - JBoss EAP
  - Jetty
  - Glassfish
  - Payara
  - WebLogic
  - WebSphere

**How to select a right APM tool?**
How to choose the right open source APM tool for you?
Choosing the right open source APM tool is critical to your team's ability to monitor and troubleshoot issues in your deployed application. If you are going for an open source tool, you must ensure that the tool is being actively developed on GitHub. You can ask yourself the following questions before choosing any open source tool:

How recent was the last commit made?
- Are the maintainers of the repo responsive?
- How active is the community around the tool?
- Is the tool based on the latest industry-standard components?
But this is just one aspect. Another aspect is whether the tool serves all your needs for application monitoring or not. You don't want your team to manage multiple tools for end-to-end visibility into the performance of your apps.

**Recommended Tools**
- Prometheus
- Jaeger
- Zipkin
- Glowroot
- App Metrics for .NET
