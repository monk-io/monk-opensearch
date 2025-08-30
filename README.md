## Monk - OpenSearch
===

This repository contains a Monk.io template to deploy OpenSearch either locally or on the cloud of your choice (AWS, GCP, Azure, Digital Ocean)

- [Prerequisites](#prerequisites)
    - [Make sure monkd is running.](#make-sure-monkd-is-running)
    - [Clone Repository](#clone-repository)
    - [Load Template](#load-template)
- [Deploy OpenSearch](#deploy-opensearch)
  - [Start runnable single-node-stack](#start-runnable-single-node-stack)
  - [Start runnable double-node-stack](#start-runnable-double-node-stack)
  - [Stop, remove and clean up workloads and templates](#stop-remove-and-clean-up-workloads-and-templates)


## Prerequisites
- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)


### Make sure monkd is running.

``` bash
$ monk status
daemon: ready
auth: logged in
not connected to cluster
```

### Clone Repository

``` bash
$ git clone git@github.com:monk-io/templates.git
```

### Load Template

``` bash
$ cd monk-opensearch
$ monk load opensearch.yaml
```

## Deploy OpenSearch

### Start runnable single-node-stack

``` bash
$ monk run opensearch/single-node-stack
```

``` bash
✔ Starting the run job: local/opensearch/single-node-stack... DONE
✔ Preparing nodes DONE
✔ Checking/pulling images...
✔ Checking/pulling images DONE
✔ Starting containers DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/single-node connections graph updating DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/single-node services initialization DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/single-node connections graph has been updated DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/single-node services have been initialized DONE
✔ Host ports have been added to container local-4f6be1c7a6e8864641b4265352-search-single-node-node DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/opensearch-dashboards connections graph updating DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/opensearch-dashboards services initialization DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/opensearch-dashboards connections graph has been updated DONE
✔ Runnable templates/local/opensearch/single-node-stack/runnables/templates/local/opensearch/opensearch-dashboards services have been initialized DONE
✔ Host ports have been added to container local-28f4602a516312d9ec3bdede97-h-dashboards-dashboards DONE
✔ New container local-28f4602a516312d9ec3bdede97-h-dashboards-dashboards created DONE
✔ New container local-4f6be1c7a6e8864641b4265352-search-single-node-node created DONE
✔ Container local-28f4602a516312d9ec3bdede97-h-dashboards-dashboards network has been configured DONE
✔ Container local-4f6be1c7a6e8864641b4265352-search-single-node-node network has been configured DONE
✔ Container local-28f4602a516312d9ec3bdede97-h-dashboards-dashboards has been started DONE
✔ Container local-4f6be1c7a6e8864641b4265352-search-single-node-node has been started DONE
✔ Started local/opensearch/single-node-stack
🔩 templates/local/opensearch/single-node-stack
 └─🧊 Peer local
    ├─🔩 templates/local/opensearch/single-node
    │  └─📦 local-4f6be1c7a6e8864641b4265352-search-single-node-node running
    │     ├─🧩 opensearchproject/opensearch:latest
    │     ├─💾 /hostroot/Users/alexnelepa/.monk/volumes/opensearch -> /usr/share/opensearch/data
    │     ├─🔌 open 188.146.36.130:9200 -> 9200
    │     └─🔌 open 188.146.36.130:9600 -> 9600
    └─🔩 templates/local/opensearch/opensearch-dashboards
       └─📦 local-28f4602a516312d9ec3bdede97-h-dashboards-dashboards running
          ├─🧩 opensearchproject/opensearch-dashboards:latest
          └─🔌 open (public) 188.146.36.130:5601 -> 5601
          
💡 You can inspect and manage your above stack with these commands:
	monk logs (-f) local/opensearch/single-node-stack - Inspect logs
	monk shell     local/opensearch/single-node-stack - Connect to the container's shell
	monk do        local/opensearch/single-node-stack/action_name - Run defined action (if exists)
💡 Check monk help for more!
```

```
http://0.0.0.0:5601
```

### Start runnable opensearch/double-node-stack

``` bash
$ monk run opensearch/double-node-stack
```

``` bash
✔ Starting the run job: local/opensearch/double-node-stack... DONE
✔ Preparing nodes DONE
✔ Checking/pulling images...
✔ [================================================] 100% opensearchproject/opensearch-dashboards:latest test-oleksii-2
✔ [================================================] 100% opensearchproject/opensearch:latest test-oleksii-1
✔ [================================================] 100% opensearchproject/opensearch:latest test-oleksii-2
✔ Checking/pulling images DONE
✔ Starting containers DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node1 connections graph updating DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node2 connections graph updating DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node1 connections graph has been updated DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node1 services initialization DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node2 connections graph has been updated DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node2 services initialization DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node1 services have been initialized DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-node2 services have been initialized DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-double-dashboards connections graph updating DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-double-dashboards connections graph has been updated DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-double-dashboards services initialization DONE
✔ Runnable templates/local/opensearch/double-node-stack/runnables/templates/local/opensearch/opensearch-double-dashboards services have been initialized DONE
✔ Host ports have been added to container b733c8a8d9df1b9538fe24e9b0c6d223-h-opensearch-node2-node DONE
✔ New container b733c8a8d9df1b9538fe24e9b0c6d223-h-opensearch-node2-node created DONE
✔ Host ports have been added to container 09df7cd7d67a2ee5f9365cd028696508-h-opensearch-node1-node DONE
✔ Host ports have been added to container ad00c688f1ba941e451d5cc22ec50bdf-e-dashboards-dashboards DONE
✔ New container 09df7cd7d67a2ee5f9365cd028696508-h-opensearch-node1-node created DONE
✔ New container ad00c688f1ba941e451d5cc22ec50bdf-e-dashboards-dashboards created DONE
✔ Container b733c8a8d9df1b9538fe24e9b0c6d223-h-opensearch-node2-node network has been configured DONE
✔ Container ad00c688f1ba941e451d5cc22ec50bdf-e-dashboards-dashboards network has been configured DONE
✔ Container 09df7cd7d67a2ee5f9365cd028696508-h-opensearch-node1-node network has been configured DONE
✔ Container b733c8a8d9df1b9538fe24e9b0c6d223-h-opensearch-node2-node has been started DONE
✔ Container ad00c688f1ba941e451d5cc22ec50bdf-e-dashboards-dashboards has been started DONE
✔ Container 09df7cd7d67a2ee5f9365cd028696508-h-opensearch-node1-node has been started DONE
✔ Started local/opensearch/double-node-stack
🔩 templates/local/opensearch/double-node-stack
 ├─🧊 Peer test-oleksii-1
 │  └─🔩 templates/local/opensearch/opensearch-node1
 │     └─📦 09df7cd7d67a2ee5f9365cd028696508-h-opensearch-node1-node running
 │        ├─🧩 opensearchproject/opensearch:latest
 │        ├─💾 /var/lib/monkd/volumes/opensearch -> /usr/share/opensearch/data
 │        ├─🔌 open (public) 52.159.234.83:9200 -> 9200
 │        └─🔌 open (public) 52.159.234.83:9600 -> 9600
 └─🧊 Peer test-oleksii-2
    ├─🔩 templates/local/opensearch/opensearch-node2
    │  └─📦 b733c8a8d9df1b9538fe24e9b0c6d223-h-opensearch-node2-node running
    │     ├─🧩 opensearchproject/opensearch:latest
    │     ├─💾 /var/lib/monkd/volumes/opensearch -> /usr/share/opensearch/data
    │     ├─🔌 open (public) 172.184.171.92:9600 -> 9600
    │     └─🔌 open (public) 172.184.171.92:9200 -> 9200
    └─🔩 templates/local/opensearch/opensearch-double-dashboards
       └─📦 ad00c688f1ba941e451d5cc22ec50bdf-e-dashboards-dashboards running
          ├─🧩 opensearchproject/opensearch-dashboards:latest
          └─🔌 open (public) 172.184.171.92:5601 -> 5601

💡 You can inspect and manage your above stack with these commands:
	monk logs (-f) local/opensearch/double-node-stack - Inspect logs
	monk shell     local/opensearch/double-node-stack - Connect to the container's shell
	monk do        local/opensearch/double-node-stack/action_name - Run defined action (if exists)
💡 Check monk help for more!
```

```
172.184.171.92:5601
```

## Stop, remove and clean up workloads and templates

``` bash
$ monk stop     opensearch/single-node-stack
$ monk purge    opensearch/single-node-stack

$ monk stop     opensearch/double-node-stack
$ monk purge    opensearch/double-node-stack
```
