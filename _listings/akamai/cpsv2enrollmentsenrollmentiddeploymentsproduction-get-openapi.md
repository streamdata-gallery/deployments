---
swagger: "2.0"
x-collection-name: Akamai
x-complete: 0
info:
  title: Akamai API Get a Certificate
  description: Get a Certificate
  version: 1.0.0
host: developer.akamai.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /cps/v2/enrollments/{enrollmentId}/deployments/production:
    get:
      summary: Get a Certificate
      description: Get a Certificate
      operationId: cpsv2enrollmentsenrollmentiddeploymentsproduction
      x-api-path-slug: cpsv2enrollmentsenrollmentiddeploymentsproduction-get
      parameters:
      - in: query
        name: enrollmentId
        description: Unique integer identifer for the enrollment
        type: string
      responses:
        200:
          description: OK
      tags:
      - Cps
      - Enrollments
      - Enrollment
      - Deployments
      - Production
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