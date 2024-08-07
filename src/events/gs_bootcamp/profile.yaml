# ONE
http.get./gs_bootcamp/profile/{id}:
  summary: Fetch Profile
  description: Fetch Profile from database
  fn: com.biz.gs_bootcamp.profile.one
  params:
    - name: id
      in: path
      required: true
      schema:
        type: string
  responses:
    '200':
      content:
        application/json:
          schema:
            type: object

# CREATE
http.post./gs_bootcamp/profile:
  summary: Create a new Profile
  description: Create Profile from database
  fn: com.biz.gs_bootcamp.profile.create
  body:
    content:
      application/json:
        schema:
          $ref: '#/definitions/gs_bootcamp/Profile'
  responses:
    '201':
      content:
        application/json:
          schema:
            type: object

# UPDATE
http.put./gs_bootcamp/profile/{id}:
  summary: Update a Profile
  description: Update Profile from database
  fn: com.biz.gs_bootcamp.profile.update
  body:
    content:
      application/json:
        schema:
          $ref: '#/definitions/gs_bootcamp/Profile'
  params:
    - name: id
      in: path
      required: true
      schema:
        type: string
  responses:
    '204':
      content:
        application/json:
          schema:
            type: object

# DELETE
http.delete./gs_bootcamp/profile/{id}:
  summary: Delete a Profile
  description: Delete Profile from database
  fn: com.biz.gs_bootcamp.profile.delete
  params:
    - name: id
      in: path
      required: true
      schema:
        type: string
  responses:
    '202':
      content:
        application/json:
          schema:
            type: object

# SEARCH
http.post./gs_bootcamp/profile/search:
  summary: Fetch multiple Profile
  description: Fetch multiple Profile from database
  fn: com.biz.gs_bootcamp.profile.search
  body:
    content:
      application/json:
        schema:
          type: object
  responses:
    '200':
      content:
        application/json:
          schema:
            type: array

