more information at <https://learn.microsoft.com/en-us/azure/container-apps/quickstart-code-to-cloud?tabs=bash%2Ccsharp>.

## Setup prerequisites

```
export TENANT_ID="30442683-87b9-47f2-88ff-0a9b2ab4f6ea"

az login --tenant $TENANT_ID

az upgrade

az extension add --name containerapp --upgrade --allow-preview true

az provider register --namespace Microsoft.App
az provider register --namespace Microsoft.OperationalInsights

```
## environment variables

export RESOURCE_GROUP="container-apps-playground"
export LOCATION="italynorth"
export ENVIRONMENT="italy-environment"
export API_NAME="nicold-api"


## deploy or update container

```
cd src
az containerapp up \
  --name $API_NAME \
  --resource-group $RESOURCE_GROUP \
  --location $LOCATION \
  --environment $ENVIRONMENT \
  --source .
```