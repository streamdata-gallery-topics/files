---
swagger: "2.0"
info:
  title: AWS Identity and Access Management API Delete Instance Profile
  version: 1.0.0
  description: Deletes the specified instance profile.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=DeleteInstanceProfile:
    get:
      summary: ' Delete Instance Profile '
      description: Deletes the specified instance profile
      operationId: deleteInstanceProfile
      parameters:
      - in: query
        name: InstanceProfileName
        description: The name of the instance profile to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - instance profiles
definitions: []
x-collection-name: AWS Identity and Access Management
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