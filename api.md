# API Documentation

URL: `https://api.clearsky.services`

## Response Errors
- **400:** Bad Request
- **404:** Not Found
- **423:** Locked
- **500:** Internal Server Error
- **501:** Not Implemented
- **503:** Service Unavailable

## Rate Limiting

Anonymous endpoints:
- **Limits:** 5 requests per second

Authenticated endpoints:
- **Limits:** 30 requests per second

## Endpoints

### Anonymous:

#### 1.

- **Endpoint:** `/api/v1/anon/get-did/<handle>`
- **Method:** `GET`
- **Description:** Get the DID of a given handle
- **Parameters:** handle
- **Response:**
    ```json
        {
            "data":
                {
                    "avatar_url":"https://cdn.bsky.app/img/avatar/plain/did:plc:w4xbfzo7kqfes5zb7r6qv3rw/bafkreicbh2mxpza6xhdwfwdvro33jlioue3g4elfp75u3je64dbvjk44la",
                    "did_identifier":"did:plc:w4xbfzo7kqfes5zb7r6qv3rw",
                    "identifier":"rudyfraser.com",
                    "user_url":"https://bsky.app/profile/did:plc:w4xbfzo7kqfes5zb7r6qv3rw"
                }
        }

#### 2.

- **Endpoint:** `/api/v1/anon/get-handle/<did>`
- **Method:** `GET`
- **Description:** Get the handle of a given DID
- **Parameters:** DID
- **Response:**
    ```json
        {
            "data":
                {
                    "avatar_url":"https://cdn.bsky.app/img/avatar/plain/did:plc:w4xbfzo7kqfes5zb7r6qv3rw/bafkreicbh2mxpza6xhdwfwdvro33jlioue3g4elfp75u3je64dbvjk44la",
                    "handle_identifier":"rudyfraser.com",
                    "identifier":"did:plc:w4xbfzo7kqfes5zb7r6qv3rw",
                    "user_url":"https://bsky.app/profile/did:plc:w4xbfzo7kqfes5zb7r6qv3rw"
                }
        }

#### 3.

- **Endpoint:** `/api/v1/anon/total-users`
- **Method:** `GET`
- **Description:** Get user count information: total users, active users, deleted users
- **Parameters:** none
- **Response:**
    ```json
        {
            "data":
                {
                    "active_count":
                        {
                            "displayname":"Active Users","value":"5,506,791"
                        },
                    "deleted_count":
                        {
                            "displayname":"Deleted Users","value":"394,545"
                        },
                    "total_count":
                        {
                            "displayname":"Total Users","value":"5,901,336"
                        }
                }
        }

#### 4.

- **Endpoint:** `/api/v1/anon/validation/validate-handle/<handle>`
- **Method:** `GET`
- **Description:** Validate a handle
- **Parameters:** handle
- **Response:**
    ```json
        {
            "data":
                {
                    "valid":"true"
                },
            "identity":"thieflord.dev"
        }

### Authenticated:

For information about authenticated endpoints please contact us at [support@clearsky.app](mailto:support@clearsky.app)