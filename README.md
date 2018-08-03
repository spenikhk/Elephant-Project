# Elephant-Project
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "sites_ElephantProject123_name": {
            "defaultValue": "ElephantProject123",
            "type": "String"
        },
        "components_ElephantProject123_name": {
            "defaultValue": "ElephantProject123",
            "type": "String"
        },
        "serverfarms_ElephantProject123_hostingPlan_name": {
            "defaultValue": "ElephantProject123-hostingPlan",
            "type": "String"
        },
        "hostNameBindings_elephantproject123.azurewebsites.net_name": {
            "defaultValue": "elephantproject123.azurewebsites.net",
            "type": "String"
        }
    },
    "variables": {},
    "resources": [
        {
            "comments": "Generalized from resource: '/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourceGroups/ElephantProject123bcdf/providers/microsoft.insights/components/ElephantProject123'.",
            "type": "microsoft.insights/components",
            "kind": "web",
            "name": "[parameters('components_ElephantProject123_name')]",
            "apiVersion": "2015-05-01",
            "location": "southcentralus",
            "tags": {
                "hidden-link:/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourceGroups/ElephantProject123bcdf/providers/Microsoft.Web/sites/ElephantProject123": "Resource"
            },
            "scale": null,
            "properties": {
                "Application_Type": "web",
                "Flow_Type": null,
                "Request_Source": "AzureTfsExtensionAzureProject",
                "HockeyAppId": null,
                "SamplingPercentage": null
            },
            "dependsOn": []
        },
        {
            "comments": "Generalized from resource: '/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourceGroups/ElephantProject123bcdf/providers/Microsoft.Web/serverfarms/ElephantProject123-hostingPlan'.",
            "type": "Microsoft.Web/serverfarms",
            "sku": {
                "name": "S1",
                "tier": "Standard",
                "size": "S1",
                "family": "S",
                "capacity": 1
            },
            "kind": "app",
            "name": "[parameters('serverfarms_ElephantProject123_hostingPlan_name')]",
            "apiVersion": "2016-09-01",
            "location": "South Central US",
            "scale": null,
            "properties": {
                "name": "[parameters('serverfarms_ElephantProject123_hostingPlan_name')]",
                "workerTierName": null,
                "adminSiteName": null,
                "hostingEnvironmentProfile": null,
                "perSiteScaling": false,
                "reserved": false,
                "targetWorkerCount": 0,
                "targetWorkerSizeId": 0
            },
            "dependsOn": []
        },
        {
            "comments": "Generalized from resource: '/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourceGroups/ElephantProject123bcdf/providers/Microsoft.Web/sites/ElephantProject123'.",
            "type": "Microsoft.Web/sites",
            "kind": "app",
            "name": "[parameters('sites_ElephantProject123_name')]",
            "apiVersion": "2016-08-01",
            "location": "South Central US",
            "tags": {
                "hidden-related:/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourcegroups/ElephantProject123bcdf/providers/Microsoft.Web/serverfarms/ElephantProject123-hostingPlan": "empty"
            },
            "scale": null,
            "properties": {
                "enabled": true,
                "hostNameSslStates": [
                    {
                        "name": "[concat(parameters('sites_ElephantProject123_name'),'elephantproject123.azurewebsites.net')]",
                        "sslState": "Disabled",
                        "virtualIP": null,
                        "thumbprint": null,
                        "toUpdate": null,
                        "hostType": "Standard"
                    },
                    {
                        "name": "[concat(parameters('sites_ElephantProject123_name'),'elephantproject123.scm.azurewebsites.net')]",
                        "sslState": "Disabled",
                        "virtualIP": null,
                        "thumbprint": null,
                        "toUpdate": null,
                        "hostType": "Repository"
                    }
                ],
                "serverFarmId": "[resourceId('Microsoft.Web/serverfarms', parameters('serverfarms_ElephantProject123_hostingPlan_name'))]",
                "reserved": false,
                "siteConfig": null,
                "scmSiteAlsoStopped": false,
                "hostingEnvironmentProfile": null,
                "clientAffinityEnabled": true,
                "clientCertEnabled": false,
                "hostNamesDisabled": false,
                "containerSize": 0,
                "dailyMemoryTimeQuota": 0,
                "cloningInfo": null
            },
            "dependsOn": [
                "[resourceId('Microsoft.Web/serverfarms', parameters('serverfarms_ElephantProject123_hostingPlan_name'))]"
            ]
        },
        {
            "comments": "Generalized from resource: '/subscriptions/879622e3-369e-443e-92d0-ac32d5e55a87/resourceGroups/ElephantProject123bcdf/providers/Microsoft.Web/sites/ElephantProject123/hostNameBindings/elephantproject123.azurewebsites.net'.",
            "type": "Microsoft.Web/sites/hostNameBindings",
            "name": "[concat(parameters('sites_ElephantProject123_name'), '/', parameters('hostNameBindings_elephantproject123.azurewebsites.net_name'))]",
            "apiVersion": "2016-08-01",
            "location": "South Central US",
            "scale": null,
            "properties": {
                "siteName": "ElephantProject123",
                "domainId": null,
                "hostNameType": "Verified"
            },
            "dependsOn": [
                "[resourceId('Microsoft.Web/sites', parameters('sites_ElephantProject123_name'))]"
            ]
        }
    ]
}


