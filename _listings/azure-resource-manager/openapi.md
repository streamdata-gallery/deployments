swagger: "2.0"
x-collection-name: Azure Resource Manager
x-complete: 1
info:
  title: SubscriptionClient
  description: all-resource-groups-and-resources-exist-within-subscriptions--these-operation-enable-you-get-information-about-your-subscriptions-and-tenants--a-tenant-is-a-dedicated-instance-of-azure-active-directory-azure-ad-for-your-organization-
  version: 1.0.0
host: management.azure.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}:
    delete:
      summary: Deletes a deployment from the deployment history.
      description: A template deployment that is currently running cannot be deleted.
        Deleting a template deployment removes the associated deployment operations.
        Deleting a template deployment does not affect the state of the resource group.
        This is an asynchronous operation that returns a status of 202 until the template
        deployment is successfully deleted. The Location response header contains
        the URI that is used to obtain the status of the process. While the process
        is running, a call to the URI in the Location header returns a status of 202.
        When the process finishes, the URI in the Location header returns a status
        of 204 on success. If the asynchronous request failed, the URI in the Location
        header returns an error-level status code.
      operationId: Deployments_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentname-delete
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment to delete
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group with the deployment to delete
      responses:
        200:
          description: OK
      tags:
      - Deployments
    head:
      summary: Deployments Check Existence
      description: Checks whether the deployment exists.
      operationId: Deployments_CheckExistence
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentname-head
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment to check
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group with the deployment to check
      responses:
        200:
          description: OK
      tags:
      - Deployments
    put:
      summary: Deploys resources to a resource group.
      description: You can provide the template and parameters directly in the request
        or link to JSON files.
      operationId: Deployments_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentname-put
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment
      - in: query
        name: No Name
      - in: body
        name: parameters
        description: Additional parameters supplied to the operation
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: resourceGroupName
        description: The name of the resource group to deploy the resources to
      responses:
        200:
          description: OK
      tags:
      - Deployments
    get:
      summary: Deployments Get
      description: Gets a deployment.
      operationId: Deployments_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentname-get
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment to get
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      responses:
        200:
          description: OK
      tags:
      - Deployments
  ? /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/cancel
  : post:
      summary: Cancels a currently running template deployment.
      description: You can cancel a deployment only if the provisioningState is Accepted
        or Running. After the deployment is canceled, the provisioningState is set
        to Canceled. Canceling a template deployment stops the currently running template
        deployment and leaves the resource group partially deployed.
      operationId: Deployments_Cancel
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentnamecancel-post
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment to cancel
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      responses:
        200:
          description: OK
      tags:
      - Deployments
  ? /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/validate
  : post:
      summary: Deployments Validate
      description: Validates whether the specified template is syntactically correct
        and will be accepted by Azure Resource Manager..
      operationId: Deployments_Validate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentnamevalidate-post
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment
      - in: query
        name: No Name
      - in: body
        name: parameters
        description: Parameters to validate
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: resourceGroupName
        description: The name of the resource group the template will be deployed
          to
      responses:
        200:
          description: OK
      tags:
      - Deployments
  ? /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/{deploymentName}/exportTemplate
  : post:
      summary: Deployments Export Template
      description: Exports the template used for specified deployment.
      operationId: Deployments_ExportTemplate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeploymentsdeploymentnameexporttemplate-post
      parameters:
      - in: path
        name: deploymentName
        description: The name of the deployment from which to get the template
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      responses:
        200:
          description: OK
      tags:
      - Deployments
  /subscriptions/{subscriptionId}/resourcegroups/{resourceGroupName}/providers/Microsoft.Resources/deployments/:
    get:
      summary: Deployments List
      description: Get all the deployments for a resource group.
      operationId: Deployments_List
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-resourcesdeployments-get
      parameters:
      - in: query
        name: $filter
        description: The filter to apply on the operation
      - in: query
        name: $top
        description: The number of results to get
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group with the deployments to get
      responses:
        200:
          description: OK
      tags:
      - Deployments