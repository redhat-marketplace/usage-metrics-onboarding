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

**TODO**: Provide a couple of examples of adoption metrics here

## Exposing adoption metrics
### Architecture
**TODO**: Put in arch. diagram here

<img src="RHM Metering Architecture.png" width="512"/>

### Concepts
### Scrape points
### Meter definitions
### Metrics dictionary





and optimize their time on focusing on what customers really want and use.



- License metrics are used to track the usage of a product against a fixed contracted capacity. An example would be that a customer purchases a database software and the contract allows
- Billable metrics are those used to generate an invoice at the end of the month. The more of the product you use, the more that the invoice will be and billable metrics are used to track this form of usage. A generic example may be the number of API calls made in the month, where each 1000 API calls adds a certain charge to the invoice.
