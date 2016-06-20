## Projects [/projects/{id}{?access_token}]

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
                "error": "Note not found"
            }