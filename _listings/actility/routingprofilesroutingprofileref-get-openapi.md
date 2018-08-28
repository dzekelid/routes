---
swagger: "2.0"
x-collection-name: Actility
x-complete: 0
info:
  title: ThingPark DX Core API Routing profile retrieval
  description: Retrieves the routing profile corresponding to the provided routing
    profile ref, if that routing profile is within authorized scopes.
  version: 1.0.0
host: dx-api.thingpark.com
basePath: /core/v141/api
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /routingProfiles:
    get:
      summary: Routing profiles retrieval
      description: Retrieves a list of existing routing profiles within authorized
        scopes.
      operationId: retrieves-a-list-of-existing-routing-profiles-within-authorized-scopes
      x-api-path-slug: routingprofiles-get
      parameters:
      - in: query
        name: routingProfileId
        description: Id of the routing profile to search for
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profiles
      - Retrieval
    post:
      summary: Routing profiles creation
      description: Creates a new routing profile.
      operationId: creates-a-new-routing-profile
      x-api-path-slug: routingprofiles-post
      parameters:
      - in: body
        name: routingProfile
        description: Contents of the routing profile to create
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profiles
      - Creation
  /routingProfiles/{routingProfileRef}:
    get:
      summary: Routing profile retrieval
      description: Retrieves the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes.
      operationId: retrieves-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-prof
      x-api-path-slug: routingprofilesroutingprofileref-get
      parameters:
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to retrieve
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Retrieval
    put:
      summary: Routing profile update
      description: Updates the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes. Note that
        the 'default' attribute can only be updated from 'false' to 'true' (thus updating
        'default' attribute for the previous default routing profile from 'true' to
        'false').
      operationId: updates-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-profil
      x-api-path-slug: routingprofilesroutingprofileref-put
      parameters:
      - in: body
        name: routingProfile
        description: Contents of the routing profile to update
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to update
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Update
    delete:
      summary: Routing profile deletion
      description: Deletes the routing profile corresponding to the provided routing
        profile ref, if that routing profile is within authorized scopes.
      operationId: deletes-the-routing-profile-corresponding-to-the-provided-routing-profile-ref-if-that-routing-profil
      x-api-path-slug: routingprofilesroutingprofileref-delete
      parameters:
      - in: path
        name: routingProfileRef
        description: Ref of the routing profile to delete
      responses:
        200:
          description: OK
      tags:
      - Routing
      - Profile
      - Deletion
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