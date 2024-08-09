# GITHUB LOGIN
http.get./gs_bootcamp/user/github_auth:
  summary: github_Auth
  description: authenticate User from github
  fn: com.biz.gs_bootcamp.user.github_auth
  authn: false
  params:
    - name: client_id
      in: query
      required: true
      schema:
        type: string
  # responses:
  #   '200':
  #     content:
  #       application/json:
  #         schema:
  #           type: object

# GITHUB CALLBACK
http.get./callback:
  summary: Github Callback
  description: callback from github with access_token
  fn: com.biz.gs_bootcamp.user.git_callback
  authn: false
  params:
    - name: token
      in: query
      required: true
      schema:
        type: string
  # body:
  #   content:
  #     application/json:
  #       schema:
  #         $ref: '#/definitions/gs_bootcamp/Profile'
  # body:
  #   content:
  #     application/json:
  #       schema:
  #         type: object
  #         properties:
  #           client_id: 
  #             type: string 
  #           client_secret: 
  #             type: string 
  responses:
    '200':
      content:
        application/json:
          schema:
            type: object

# CREATE/ SIGN UP
http.post./gs_bootcamp/user/signup:
  summary: Create a new User
  description: Create User from database
  fn: com.biz.gs_bootcamp.user.create
  body:
    content:
      application/json:
        schema:
          $ref: '#/definitions/gs_bootcamp/User'
  responses:
    '201':
      content:
        application/json:
          schema:
            type: object

# LOGIN
http.post./gs_bootcamp/user/login:
  summary: Fetch User
  description: Fetch User from database
  fn: com.biz.gs_bootcamp.user.login
  body:
    content:
      application/json:
        schema:
          $ref: '#/definitions/gs_bootcamp/User'
  responses:
    '200':
      content:
        application/json:
          schema:
            type: object


# ONE
http.get./gs_bootcamp/user/{id}:
  summary: Fetch User
  description: Fetch User from database
  fn: com.biz.gs_bootcamp.user.one
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

# UPDATE
http.put./gs_bootcamp/user/{id}:
  summary: Update a User
  description: Update User from database
  fn: com.biz.gs_bootcamp.user.update
  body:
    content:
      application/json:
        schema:
          $ref: '#/definitions/gs_bootcamp/User'
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
http.delete./gs_bootcamp/user/{id}:
  summary: Delete a User
  description: Delete User from database
  fn: com.biz.gs_bootcamp.user.delete
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
http.post./gs_bootcamp/user/search:
  summary: Fetch multiple User
  description: Fetch multiple User from database
  fn: com.biz.gs_bootcamp.user.search
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

