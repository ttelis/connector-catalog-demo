# Connector catalog demo

A test marketplace for the RadiantOne connector catalog (Jira epic V9-70). It holds only a
`manifest.yaml`. Its builds point at the JARs in the public
[radiantlogicinc/connector-marketplace](https://github.com/radiantlogicinc/connector-marketplace)
by full URL, with their real SHA-256 checksums, so no JAR is copied here.

The release statuses are made up to test each case the catalog handles. They are not real release
decisions:

| Connector | Releases | What it tests |
|---|---|---|
| Microsoft Azure AI Foundry | 0.9.2 withdrawn | No active release; withdrawn warning on an installed Template |
| ServiceNow | 1.0.0 deprecated | No active release; no warning on an installed Template |
| Google Cloud Agents | 0.9.4 active, 0.9.3 deprecated, 0.9.2 withdrawn | Only active builds are offered |
| AWS Bedrock | 1.0.1 active, 1.0.0 deprecated | Deprecated build is not offered |
| Workday | 1.0.0 active, typed `jdbc` | The Database filter has an entry |
| Okta | `replaces: [servicenow]` | Edit connector offers it for a Template that runs ServiceNow |
| Workday | `replaces: [google-cloud-agents]` | A listed replacement that does not fit, to see the reason for the refusal |

To use it, set the data catalog service's `catalog.url` to this repository's URL.
`catalog.manifest_location` stays `manifest.yaml`.
