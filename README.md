# Usage metering guide

This repo contains various guides and artefacts related to onboarding with the usage metrics capabilities of the Red Hat Markeplace.

## Adoption metrics

Adoption (value) metrics are a way to describe the productive use of the deployed product. For example, Service Calls (in Integration product) or Database Storage (in Database product) or Detected Threats (in Security product). Adoption metrics are not intended to be used for rating and invoicing. While there are no restrictions in the units of measure that may be collected and display, there is a _Metrics Dictionary_ that provides a common set of metrics and supporting information about the metric. Adopters are encouraged to use one of the metrics already available in the dictionary. In the case that a desired metric is not available, it may be added after review by the Red Hat Marketplace team.

### Adding new metrics

Please contact the Red Hat Marketplace onboarding team with the following details
- The `group` which is defined for the operator
- The `kind` which is defined for the operator
- The `metricId` which Programmatically and uniquely identifies the metric (e.g. API_CALLS_MILLION)
- The `singularName` to use displaying a singular value
- The `pluralName` to use displaying a plural value
- The `abbreviation` for a metric
- The `suffix` text following a displayed value
- The `description` explaining the significance the of the metric and what is being measured
- The `aggregationType` of metric governing the way it is recorded and processed, This is either `cumulative` or `current`

You can look at the [metricsDictionary.json](123.licensing.ibm.com/IBMLicensing/metricsDictionary.json) for examples.

#### Cumulative metrics

Cumulative metrics are those that will keep increasing in value. For example, "Total service calls" is a value that is always cumulative and can only keep increasing. Note that the reported usage value is a lifetime total value and does **NOT** represent the metered usage for a time window. Each time a smaple is measured, the value will be either the same or higher than the previously measured value and never less than the previously sampled value.

#### Current metrics

Current type metrics that represent a snapshot or a point in time measurement. An example would be "Number of logged in users" as this represents the number of users logged in at the time of samplling. Each time a measurement is recorded, the value may be different.
