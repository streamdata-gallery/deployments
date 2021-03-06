swagger: "2.0"
x-collection-name: Hewlett Packard Enterprise (HPE)
x-complete: 1
info:
  title: HPE OneSphere API
  description: hpe-onesphere-hybrid-cloud-management-rest-api-for-calls-requiring-authentication-use-restsession-to-get-a-token-
  termsOfService: http://www.hpe.com/onesphere
  contact:
    name: HPE OneSphere API team
    url: http://www.hpe.com/onesphere
  version: 1.0.0
host: deic02-hpe.hpeonesphere.com
basePath: /rest
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /deployments:
    get:
      summary: Get Deployments
      description: Returns deployments. It requires any project role or non-'consumer'
        global role.
      operationId: FindDeployments
      x-api-path-slug: deployments-get
      parameters:
      - in: query
        name: query
        description: Filters the deployments returned
      - in: query
        name: userQuery
        description: Filters the deployments returned
      - in: query
        name: view
        description: 'Return related resources:  * `full` - include zone, service,
          volume details'
      responses:
        200:
          description: OK
      tags:
      - Deployments
    post:
      summary: Post Deployments
      description: Creates a new deployment. It requires any project role, or the
        **administrator** or **project creator** global role.
      operationId: CreateDeployment
      x-api-path-slug: deployments-post
      parameters:
      - in: body
        name: deployment
        description: Add new deployment
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Deployments
  /deployments/{id}:
    delete:
      summary: Delete Deployments
      description: Delete a deployment and associated resources. It requires any project
        role, or the **administrator** or **project creator** global role.
      operationId: DeleteDeployment
      x-api-path-slug: deploymentsid-delete
      parameters:
      - in: path
        name: id
        description: ID of deployment to delete
      responses:
        200:
          description: OK
      tags:
      - Deployments
    get:
      summary: Get Deployments
      description: Returns a deployment based on its id. It requires any project role
        or non-'consumer' global role.
      operationId: GetDeploymentById
      x-api-path-slug: deploymentsid-get
      parameters:
      - in: path
        name: id
        description: ID of deployment to fetch
      - in: query
        name: view
        description: 'Return related resources:  * `full` - include region, zone,
          service, virtual machine profile,  firewall, volume details'
      responses:
        200:
          description: OK
      tags:
      - Deployments
    patch:
      summary: Patch Deployments
      description: Updates a deployment. **Requires any project role, or 'administrator'
        or 'project creator' global role**. Allowed fields for PATCH of deployments
        are name(add,replace), volumes(add), k8snumWorkers(add), userData(add), serviceInput(add),
        version(add).
      operationId: UpdateDeployment
      x-api-path-slug: deploymentsid-patch
      parameters:
      - in: body
        name: deployment
        description: Update deployment
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: ID of deployment to update
      responses:
        200:
          description: OK
      tags:
      - Deployments
  /deployments/{id}/actions:
    post:
      summary: Post Deployments Actions
      description: Peforms an action to change the state of a deployment. It requires
        any project role, or the **administrator** or **project creator** global role.
      operationId: ActOnDeployment
      x-api-path-slug: deploymentsidactions-post
      parameters:
      - in: body
        name: action
        description: Action to perform
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: id
        description: ID of deployment to act on
      responses:
        200:
          description: OK
      tags:
      - Deployments
      - Actions
  /deployments/{id}/console:
    post:
      summary: Post Deployments Console
      description: Returns a deployment console URL for deployment
      operationId: GetDeploymentConsoleURL
      x-api-path-slug: deploymentsidconsole-post
      parameters:
      - in: path
        name: id
        description: ID of deployment for which console URL is required
      responses:
        200:
          description: OK
      tags:
      - Deployments
      - Console
  /deployments/{id}/kubeconfig:
    get:
      summary: Get Deployments Kubeconfig
      description: Returns the kubeconfig. Applicable only to deployments of Kubernetes
        cluster. **Requires 'consumer' role on workspace**
      operationId: GetDeploymentKubeConfig
      x-api-path-slug: deploymentsidkubeconfig-get
      parameters:
      - in: path
        name: id
        description: ID of deployment for which kubeconfig is required
      responses:
        200:
          description: OK
      tags:
      - Deployments
      - Kubeconfig