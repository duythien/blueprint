## Projects [/projects{?access_token}]

Get a list projects

+ Parameters
    + access_token: `3839270947bcbfddf5284898d4837652d5f63dff` (required, string) - FoxOMS API access token

### Get Projects [GET]
Get a list of projects.

+ Response 200 (application/json)

    + Headers

            X-Response-Time: 4ms

    //+ Attributes (NoteList)
    + Body

        {
  "data": [
    {
      "id": "1",
      "legacyId": null,
      "tntId": "1",
      "name": "Update FoxOMS",
      "code": "",
      "description": "",
      "statusId": "0",
      "startDate": "0",
      "endDdate": "0",
      "presetFlag": "0",
      "presetName": "0",
      "privateFlag": "0",
      "folderFlag": "0",
      "parentId": "0",
      "usrId": "0",
      "orgId": "0",
      "order": "0",
      "colorBackground": "",
      "colorText": "#ffffff",
      "createdId": "1",
      "createdDate": "1388552400",
      "updatedId": "1",
      "updatedDate": "1466395381",
      "deleteFlag": "0"
    },
    {
      "id": "5",
      "legacyId": null,
      "tntId": "1",
      "name": "Animations",
      "code": null,
      "description": "",
      "statusId": "0",
      "startDate": "0",
      "endDdate": "0",
      "presetFlag": "0",
      "presetName": "",
      "privateFlag": "0",
      "folderFlag": "1",
      "parentId": "0",
      "usrId": null,
      "orgId": null,
      "order": null,
      "colorBackground": "",
      "colorText": "",
      "createdId": "1",
      "createdDate": "1388552400",
      "updatedId": "1",
      "updatedDate": "1388552400",
      "deleteFlag": "0"
    }
  ],
  "meta": {
    "pagination": {
      "total": 38,
      "count": 19,
      "per_page": 2,
      "current_page": 1,
      "total_pages": 19,
      "links": {
        "next": null
      }
    }
  }
}


### Create New Project [POST /projects/new{?access_token}]
Create a new note using a name and an optional content body.
+ Parameters
    + access_token: `3839270947bcbfddf5284898d4837652d5f63dff` (required, string) - FoxOMS API access token

+ Request with body (application/json)

    + Body

            {
                "name": "My new note",
                "body": "This is the body"
            }

+ Response 201

+ Response 400 (application/json)

    + Body

            {
                "error": "Invalid name"
            }

+ Request without body (application/json)

    + Body

            {
                "name": "My new note"
            }

+ Response 201

+ Response 400 (application/json)

    + Body

            {
                "error": "Invalid name"
            }


## Project [/projects/{id}{?access_token}]

Returns a single project

+ Parameters

    + id: `1` (required, int) - The project ID

    + access_token: `3839270947bcbfddf5284898d4837652d5f63dff` (required, string) - FoxOMS API access token

### Get Project [GET]
Get a single project.


+ Response 200 (application/json)

    + Headers

            X-Response-Time: 4ms

    + Body
        {
          "data": {
            "id": "1",
            "legacyId": null,
            "tntId": "1",
            "name": "",
            "code": "",
            "description": "",
            "statusId": "0",
            "startDate": "0",
            "endDdate": "0",
            "presetFlag": "0",
            "presetName": "0",
            "privateFlag": "0",
            "folderFlag": "0",
            "parentId": "0",
            "usrId": "0",
            "orgId": "0",
            "order": "0",
            "colorBackground": "",
            "colorText": "#ffffff",
            "createdId": "1",
            "createdDate": "1388552400",
            "updatedId": "1",
            "updatedDate": "1465483149",
            "deleteFlag": "0"
          }
        }
+ Response 400 (application/json)

    + Body
        {
          "error": {
            "code": "GEN-DATA",
            "http_code": 409,
            "message": "The project not exist!"
          }
        }


### Update project [PUT]
Update a single project by setting the title and/or body.

::: warning
#### <i class="fa fa-warning"></i> Caution
If the value for `name` or `body` is `null` or `undefined`, then the corresponding value is not modified on the server. However, if you send an empty string instead then it will **permanently overwrite** the original value.
:::

+ Request (application/json)

    + Body

        {
            "name" : "Update FoxOMS"
        }

+ Response 200 (application/json)

    + Headers
            X-Response-Time: 4ms

    //+ Attributes (NoteData)

    + Body

        {
          "sucess": {
            "message": "ok"
          }
        }

+ Response 404 (application/json)

    + Headers

            X-Request-ID: f72fc914
            X-Response-Time: 4ms

    + Body

            {
                "error": "Note not found"
            }

+ Request delete body (application/json)

    + Body

            {
                "body": ""
            }

+ Response 200 (application/json)

    + Headers

            X-Request-ID: f72fc914
            X-Response-Time: 4ms

    + Attributes (NoteData)

+ Response 404 (application/json)

    + Headers

            X-Request-ID: f72fc914
            X-Response-Time: 4ms

    + Body

            {
                "error": "Project not found"
            }
### Delete a Project [DELETE]
Delete a single note

+ Response 204

+ Response 404 (application/json)

    + Headers

            X-Response-Time: 4ms

    + Body

            {
                "error": "Project not found"
            }
