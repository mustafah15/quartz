---
tags:
  - tools
  - distributed-systems
related: "[[distributed systems]]"
type: literature
---

[[monitoring]] vs. [[observability]] vs [[application performance management]]


Observability means distributed tracing that allows your system to receive a request and track that work as it interacts with various functions, and services that comprise your application.

observability contains the following 
- logging that can be from 
	- os 
	- k8s
	- application 
- metrics 
- tracing  

An aggregator collects all logs from the system, and it has filters so developers can look only for what they need


Trances generally consist of spans and each span has the following properties 
- span id
- parent span id
- trace id
- operation name

Some say that observability is the evolution of [[application performance management|APM]] however APM provides a debugging of an application and observability provides an understanding 

collect, monitor, analyze 

k8s add the following
service level objectives 
service level indicators 


### Events

What is an event?
	a timestamp and a collection of attributes.
example if you have an HTTP server what kind of events are you going to have?
- connection events 
- request events 
- response events
- etc
and all those events going to have different attributes associated with them like
- unique event attributes like
	- timestamp
	- description or message
- resource attributes (static context) like 
	- service name 
	- service id 
	- service version 
	- region
- operation attributes (dynamic context) like
	- request start time
	- request duration
	- http status 
	- http method
	- project id
	- account id
- causality attributes 
	- trace id 
	- span id 
	- parent span id 
	- operation name

Adding context turns events into traces which is super important because finding logs in a large distributed system is painful and suffering, Without context like `traceID` lots of searching and filtering is required, however finding all of the events in a trace is easy which can be a  single lookup.

### Aggregates 

When we look at events over time (aggregates) we want to find patterns and be alerted when bad patterns appear example the number of errors increasing over time, so we want to **count how many times a specific attribute is showing up on an event**, alternatively, you can look a value of an attribute and see if it exceed a certain threshold that you know is bad for example latency a request is taking too long .. so  in those cases you want to **look at the spread of values** how many requests taking over 5s and how many requests taking over 1s and how many requests taking less than 30 ms in another word  you want to look in a histogram and we tend to call those kind of aggregation that we are alerting on **METRICS** 

But also we want to know what the correlations we want to know what cause the alert For example we don't just want to know that we have high latency but also we want to know if this latency is correlated with a specific Kafka node  which should tell you a lot of information where to look next for the root cause

### Correlation and Causality

Analyzing Events and Aggregates is how you find the correlation and causality because correlation may occur between 
- attributes in a single event 
- Multiple events in a trace 
- traces and resources those traces are passing through
In other words, when you are looking at a metric and the metric has sent an alert the next thing you want to look at is the transaction, You probably want to see the actual events generated by that particular metric alert and if your logs and your metrics are completely are in separate systems then connecting alerts with the transactions that caused them and finding the root cause is going to be painful and hard, and to solve this problem your aggregates (metrics) need to be built from trace data.

Therefore Tracing is the glue that connects these data together in a way that allows you to find correlations

With modern observability Now we have a different data structure that enables automated analysis that can find correlations and fetch relevant data and that saves so much time. instead of spending so much time correlating these data and trying to find a correlation yourself, making hypotheses and checking them becomes a rabid fire activity  

### OpenTelemetry

Is a data structure that enables automated analysis 
It provides the following 

- **Traces**: context for what happened 
- **Resources**: context for where it happened
- **Metrics**: attached to traces that created those metrics.
- **Logs**: attached to traces as events. They are organized by a chain of causality automatically 

All of this information is combined into a single protocol called [[OTLP]]  which is an efficient way of streaming all these different types of data to a single analysis tool to look at all of it so modern analysis is not through different tools it's one tool that uses all of this data together so it can synthesize this correlations and allow you to easily move from one data point to another from matrics to traces to logs...
Examples of tools that can do this for you (lightstep, datadog, zipkin, grafana tempo)

[[Site Reliability Engineering|SRE]]