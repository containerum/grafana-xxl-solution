# Grafana XXL

Do you need to track and visualize the metrics of your project, e.g. monitor server status, get database statistics, and track your business processes?

Then this is the Solution for you!

Dashboard for metrics visualization. This package includes all plugins from the official website [grafana.com](http://grafana.com) such as Zabbix, Clickhouse, Elasticsearch, and many others.

## How it works:

You add the plugins you need - Grafana collects and visualizes the metrics.

### It consists of:

* Grafana XXL  


To launch this solution on Containerum.com sign up with the service, download and use [Containerum CLI](https://github.com/containerum/chkit) `chkit`.


1. Run the Solution with `chkit solution`:
```
chkit solution run containerum/grafana-xxl-solution -e PASSWORD=12345678 -e CPU=500m -e RAM=500Mi
```
* PASSWORD - password,
* CPU, RAM - compute resources for this Solution

2. Make sure that the Solution is running:

```
$ chkit get deploy

+-----------------------+------+-------------+------+-------+-----+
| NAME                  | PODS | PODS ACTIVE | CPU  | RAM   | AGE |
+-----------------------+------+-------------+------+-------+-----+
| grafanasln-s75fl      | 1    | 1           | 500m | 500Mi | 22m |
+-----------------------+------+-------------+------+-------+-----+
```
3. Using `chkit get` get the address and the port to access the running Solution:
```
$ chkit get svc

+--------------------------+-----------------+----------+-------------------+---------------+-----+
| NAME                     | CLUSTER-IP      | EXTERNAL | HOST              | PORT(S)       | AGE |
+--------------------------+-----------------+----------+-------------------+---------------+-----+
|  grafanasln-s75fl        | 10.105.25.198   | true     | x3.containerum.io | 37834:3000/TCP| 22m |
+--------------------------+-----------------+----------+-------------------+---------------+-----+

```
4. Go to `x3.containerum.io:37834`, using the default username `admin` and the password you entered in step 1.

5. Create a dashboard and add the metrics you want to track.

![](/gif/grafanasln.gif)
