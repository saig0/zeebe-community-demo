# zeebe-community-demo

A demo for Zeebe with community projects from https://github.com/zeebe-io/awesome-zeebe.

Currently included:

* [Zeebe Hazelcast Exporter](https://github.com/zeebe-io/zeebe-hazelcast-exporter)
* [Zeebe Simple Monitor](https://github.com/zeebe-io/zeebe-simple-monitor)
* [Zeebe Simple Tasklist](https://github.com/zeebe-io/zeebe-simple-tasklist)
* [Zeebe Script Worker](https://github.com/zeebe-io/zeebe-script-worker)
* [Zeebe Camunda DMN Worker](https://github.com/zeebe-io/zeebe-dmn-worker)
* [Zeebe HTTP Worker](https://github.com/zeebe-io/zeebe-http-worker)

## Install

### Bundle

1. Download the [bundle](https://github.com/saig0/releases)

2. Unpack the achieve 

3. Start the broker and applications/workers using the script

    `./start`

### Manually

1. Download the following artifacts:

    * [Zeebe distribution](https://github.com/zeebe-io/zeebe/releases)
    * [Zeebe Hazelcast Exporter](https://github.com/zeebe-io/zeebe-hazelcast-exporter/releases)
    * [Zeebe Simple Monitor](https://github.com/zeebe-io/zeebe-simple-monitor/releases/)
    * [Zeebe Simple Tasklist](https://github.com/zeebe-io/zeebe-simple-tasklist/releases)
    * [Zeebe Script Worker](https://github.com/zeebe-io/zeebe-script-worker/releases)
    * [Zeebe Camunda DMN Worker](https://github.com/zeebe-io/zeebe-dmn-worker/releases)
    * [Zeebe HTTP Worker](https://github.com/zeebe-io/zeebe-http-worker/releases)
    * [Zeebe Modeler](https://github.com/zeebe-io/zeebe-modeler/releases)
    
2. Copy the Hazelcast exporter JAR into `zeebe-broker-{VERSION}/lib/`

3. Add the Hazelcast exporter to the configuration `zeebe-broker-{VERSION}/conf/zeebe.cfg.toml`

    ```
    [[exporters]]
    id = "hazelcast"
    className = "io.zeebe.hazelcast.exporter.HazelcastExporter"
    
      [exporters.args]
      # comma separated list of io.zeebe.protocol.record.ValueType
      enabledValueTypes = "JOB,WORKFLOW_INSTANCE,DEPLOYMENT,INCIDENT,TIMER,VARIABLE,MESSAGE,MESSAGE_SUBSCRIPTION,MESSAGE_START_EVENT_SUBSCRIPTION"
    ```
    
4. Start the Broker    

    `./zeebe-broker-{VERSION}/bin/broker`
    
5. Wait until it is started and start the other applications/workers
    
    * `java -jar zeebe-simple-monitor-app-0.15.0.jar`
    * `java -jar zeebe-simple-tasklist-0.3.0.jar`
    * `java -jar zeebe-script-worker-0.6.0.jar`
    * `java -jar zeebe-dmn-worker-0.4.0.jar`
    * `java -jar zeebe-http-worker-0.2.0.jar`

## Usage

1. Open Zeebe Simple Monitor: http://localhost:8080
    
2. Open Zeebe Simple Tasklist: http://localhost:8081 
    
    Login with `demo` / `demo`

## About
