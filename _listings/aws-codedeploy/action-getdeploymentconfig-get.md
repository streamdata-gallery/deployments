---
swagger: "2.0"
info:
  title: AWS CodeDeploy API Get Deployment Config
  version: 1.0.0
  description: Gets information about a deployment configuration.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=GetDeploymentConfig:
    get:
      summary: ' Get Deployment Config '
      description: Gets information about a deployment configuration
      operationId: getDeploymentConfig
      parameters:
      - in: query
        name: deploymentConfigName
        description: The name of a deployment configuration associated with the applicable
          IAM user or            AWS account
        type: string
      responses:
        200:
          description: OK
      tags:
      - deployments
definitions: []
x-collection-name: AWS CodeDeploy
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---