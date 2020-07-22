## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: kusto
  namespace: azure.mgmt.kusto
  package-name: azure-mgmt-kusto
```
``` yaml ($az) && !$(cli-core)
az-output-folder: $(azure-cli-extension-folder)/src/kusto



cli:
    cli-directive:
      - where:
            group: 'DataConnections'
            op: 'CreateOrUpdate|Update'
            param: 'parameters'
        poly-resource: true
      - where:
            group: 'DataConnections'
            op: 'dataConnectionValidation'
            param: 'properties'
        poly-resource: true

```