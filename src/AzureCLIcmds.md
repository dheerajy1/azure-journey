I upload Azure CLI Commands

<Details>
<Summary>
Day 20 Azure CLI Commands
</Summary>

```
az storage account list
```

output
```
[
  {
    "accessTier": null,
    "allowBlobPublicAccess": true,
    "allowCrossTenantReplication": null,
    "allowSharedKeyAccess": null,
    "allowedCopyScope": null,
    "azureFilesIdentityBasedAuthentication": null,
    "blobRestoreStatus": null,
    "creationTime": "2023-08-28T08:42:09.470039+00:00",
    "customDomain": null,
    "defaultToOAuthAuthentication": null,
    "dnsEndpointType": null,
    "enableHttpsTrafficOnly": false,
    "enableNfsV3": null,
    "encryption": {
      "encryptionIdentity": null,
      "keySource": "Microsoft.Storage",
      "keyVaultProperties": null,
      "requireInfrastructureEncryption": null,
      "services": {
        "blob": {
          "enabled": true,
          "keyType": "Account",
          "lastEnabledTime": "2023-08-28T08:42:09.876276+00:00"
        },
        "file": {
          "enabled": true,
          "keyType": "Account",
          "lastEnabledTime": "2023-08-28T08:42:09.876276+00:00"
        },
        "queue": null,
        "table": null
      }
    },
    "extendedLocation": null,
    "failoverInProgress": null,
    "geoReplicationStats": null,
    "id": "/subscriptions/01383f7e-b3be-4607-a9f3-b77a8c998aa5/resourceGroups/learn-f1359616-78eb-4e80-9a9a-dfc528bf09ad/providers/Microsoft.Storage/storageAccounts/cloudshell1340719050",
    "identity": null,
    "immutableStorageWithVersioning": null,
    "isHnsEnabled": null,
    "isLocalUserEnabled": null,
    "isSftpEnabled": null,
    "keyCreationTime": {
      "key1": "2023-08-28T08:42:09.595035+00:00",
      "key2": "2023-08-28T08:42:09.595035+00:00"
    },
    "keyPolicy": null,
    "kind": "Storage",
    "largeFileSharesState": null,
    "lastGeoFailoverTime": null,
    "location": "southeastasia",
    "minimumTlsVersion": "TLS1_0",
    "name": "cloudshell1340719050",
    "networkRuleSet": {
      "bypass": "AzureServices",
      "defaultAction": "Allow",
      "ipRules": [],
      "resourceAccessRules": null,
      "virtualNetworkRules": []
    },
    "primaryEndpoints": {
      "blob": "https://cloudshell1340719050.blob.core.windows.net/",
      "dfs": null,
      "file": "https://cloudshell1340719050.file.core.windows.net/",
      "internetEndpoints": null,
      "microsoftEndpoints": null,
      "queue": "https://cloudshell1340719050.queue.core.windows.net/",
      "table": "https://cloudshell1340719050.table.core.windows.net/",
      "web": null
    },
    "primaryLocation": "southeastasia",
    "privateEndpointConnections": [],
    "provisioningState": "Succeeded",
    "publicNetworkAccess": null,
    "resourceGroup": "learn-f1359616-78eb-4e80-9a9a-dfc528bf09ad",
    "routingPreference": null,
    "sasPolicy": null,
    "secondaryEndpoints": null,
    "secondaryLocation": "eastasia",
    "sku": {
      "name": "Standard_GRS",
      "tier": "Standard"
    },
    "statusOfPrimary": "available",
    "statusOfSecondary": "available",
    "storageAccountSkuConversionStatus": null,
    "tags": {
      "ms-resource-usage": "azure-cloud-shell",
      "x-created-by": "productsandboxes"
    },
    "type": "Microsoft.Storage/storageAccounts"
  }
]
```
=========================

```
az storage account keys list \
--account-name cloudshell1340719050
```

Output:
```
[
  {
    "creationTime": "2023-08-28T08:42:09.595035+00:00",
    "keyName": "key1",
    "permissions": "FULL",
    "value": "3oLB3qb9KD9DBwtc8YZ8PGkcsCl5NvuMxSY77OqhowyaV9qcI1FajgYxFpbNCLzitirH7NTGfNtP+ASt6p/2MQ=="
  },
  {
    "creationTime": "2023-08-28T08:42:09.595035+00:00",
    "keyName": "key2",
    "permissions": "FULL",
    "value": "yaSfn50548aWutm7YPSdeAD7t4BWX1rri0TnJVNiUDlS4aSb/X9sd4uEmrTp2LJcUTRKc/H1TlAE+AStCnCe6Q=="
  }
]
```
===============================
```
az storage account show-connection-string \
--resource-group learn-f1359616-78eb-4e80-9a9a-dfc528bf09ad \
--name cloudshell1340719050
```
Output
```
{
  "connectionString": "DefaultEndpointsProtocol=https;EndpointSuffix=core.windows.net;AccountName=cloudshell1340719050;AccountKey=3oLB3qb9KD9DBwtc8YZ8PGkcsCl5NvuMxSY77OqhowyaV9qcI1FajgYxFpbNCLzitirH7NTGfNtP+ASt6p/2MQ==;BlobEndpoint=https://cloudshell1340719050.blob.core.windows.net/;FileEndpoint=https://cloudshell1340719050.file.core.windows.net/;QueueEndpoint=https://cloudshell1340719050.queue.core.windows.net/;TableEndpoint=https://cloudshell1340719050.table.core.windows.net/"
}
```
=================
```
az storage container list \
--account-name cloudshell1340719050 \
--connection-string "DefaultEndpointsProtocol=https;EndpointSuffix=core.windows.net;AccountName=cloudshell1340719050;AccountKey=3oLB3qb9KD9DBwtc8YZ8PGkcsCl5NvuMxSY77OqhowyaV9qcI1FajgYxFpbNCLzitirH7NTGfNtP+ASt6p/2MQ==;BlobEndpoint=https://cloudshell1340719050.blob.core.windows.net/;FileEndpoint=https://cloudshell1340719050.file.core.windows.net/;QueueEndpoint=https://cloudshell1340719050.queue.core.windows.net/;TableEndpoint=https://cloudshell1340719050.table.core.windows.net/"
```

Output
```
[]
```
==========
```
az storage container create \
    --name mytempstoragecontainer \
    --account-name cloudshell1340719050 \
    --public-access off \
    --resource-group learn-f1359616-78eb-4e80-9a9a-dfc528bf09ad
```

Output
```
[
  {
    "deleted": null,
    "encryptionScope": {
      "defaultEncryptionScope": "$account-encryption-key",
      "preventEncryptionScopeOverride": false
    },
    "immutableStorageWithVersioningEnabled": false,
    "metadata": null,
    "name": "mytempstoragecontainer",
    "properties": {
      "etag": "\"0x8DBA7A492550206\"",
      "hasImmutabilityPolicy": false,
      "hasLegalHold": false,
      "lastModified": "2023-08-28T08:55:47+00:00",
      "lease": {
        "duration": null,
        "state": "available",
        "status": "unlocked"
      },
      "publicAccess": null
    },
    "version": null
  }
]
```
==============
set to off just if wanted to modify 
```
az storage container set-permission \
   --account-name  cloudshell1340719050  \
   --name  mytempstoragecontainer \
   --public-access off
```

======
```
az storage blob list \
--container-name mytempstoragecontainer \
--account-name cloudshell1340719050 
```
Output
```
[]
```
==============

unable to upload file  a blob 
```
az storage blob upload \
    --file "path" \
    --container-name mytempstoragecontainer \
    --account-name  cloudshell1340719050  \
    --name mytempblob
```

--

upload data

```
az storage blob upload --data "testing blob from azure learn sandbox cli" \
--container-name mytempstoragecontainer \
--name mytempblob \
--account-name cloudshell1340719050 \
--account-key "3oLB3qb9KD9DBwtc8YZ8PGkcsCl5NvuMxSY77OqhowyaV9qcI1FajgYxFpbNCLzitirH7NTGfNtP+ASt6p/2MQ==" \
--overwrite
```

===========

URL
```
az storage blob url \
--container-name mytempstoragecontainer \
--name mytempblob \
--account-name cloudshell1340719050 \
--account-key "3oLB3qb9KD9DBwtc8YZ8PGkcsCl5NvuMxSY77OqhowyaV9qcI1FajgYxFpbNCLzitirH7NTGfNtP+ASt6p/2MQ=="
```

Output
```
https://cloudshell1340719050.blob.core.windows.net/mytempstoragecontainer/mytempblob
```
------------

Set permission 
```
az storage container set-permission \
   --account-name  cloudshell1340719050  \
   --name  mytempstoragecontainer \
   --public-access blob
```

-----

</Details>


