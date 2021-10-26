# Adoption Metrics Adopters Guide

## Contents
- [Overview](#overview)
  - [Adoption metrics](#adoption-metrics)
- Exposing adoption metrics
  - Architecture (diagram)
  - Components (explain compeonents, cluster, rhm operator, product, rhm)
  - Concepts (link to prometheus, scrape points, meter def docs)
  - Scrape point schema and example
  - Meter definition schema and example
  - Selecting your metric ids (metrics dictionary explanation)


- Why expose adoption metrics
- Enabling support for adoption metrics
- Types of metrics
- Exposing adoption metrics

## Overview
The intended audience for this guide are product vendors looking collect statistics about the usage of their OpenShift based products. This guide will introduce the concept of adoption metrics, why they are of use, and how to set up your product to send these metrics to the Red Hat Marketplace to view them on a dashboard.

### Adoption metrics
There are various types of metrics that are collected to measure a product's usage for a number of different purposes. The typical three types are license metrics, billable metrics, and adoption metrics. Read more about license and billable metrics here (give link).
Adoption metrics provide various statistics of how a product is being used by customers. It provides key insights into which features are being used more or which are being used less allowing the product vendor to make improvements to their product capabilities. These metrics can be used in many ways including some of the examples below
- Evaluate performance
- Find and fix defects
- Improve quality and user experience
- Identify popular and unpoplar features

**TODO**: Provide a couple of generic examples of adoption metrics here. Don't name products

## Exposing adoption metrics
### Architecture and components
<img src="RHM Metering Architecture.png" width="512"/>

The components involved are the **Product** itself deployed by a customer to a cluster. As this product is used, it collects various relevant statistics that are exposed as adoption metrics on an API. **Prometheus**(give link) regularly calls that API to fetch data and saves it within it's database on the cluster. The **Red Hat Marketplace Operator**(give link) queries for that data from Prometheus using a configured query and schedule(link to meter defs below). Then a report of metric data is created and sent to the **Red Hat Marketplace** to process and present to customers(give RHM link).
### Concepts
#### Scrape points
A scrape point is an API provided by a product where Prometheus regularly invokes to fetch metric data. A product may any kind of metric in general but for adoption metrics to be compatible with the Red Hat Marketplace, there are a few conventions and specific fields to be followed. Prometheus documentation(give link) explains in more detail about how to expose a scrape point and the structure of the data that should be exposed there. The schema of the scrape point specific to adoption metrics follows this pattern
```
ADOPTION_METRIC_NAME{

metricType="adoption",
aggregationType=[OPTIONAL, Either current or cumulative],

metricId=[adoption_metric_codename],
metricDisplayName=[OPTIONAL, display name of the metrics],
metricAbbreviation=[OPTIONAL, display abbreviation of the metrics],

[any other additional parameters]

}[METRIC_VALUE]
```

This is an example
```bash
api_calls_total{

metricType="adoption",
metricId="API_CALLS"

} 10000
```

Another example that includes optional fields
```bash
active_users{

metricType="adoption",
aggregationType="current"
metricId="ACTIVE_USERS"
metricDisplayName="Number of currently active users",
metricAbbreviation="AU"


} 107
```

### Meter definitions
### Metrics dictionary






















