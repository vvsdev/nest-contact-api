# User API Specs

## Register User

**Method**: POST

**Endpoint**: `/api/users`

**Request Body**:

```json
{
    "username": "udin_petot",
    "password": "rahasia",
    "name": "Udin Petot Jr"
}
```

**Response Body (Success)**:

**Status Code**: `201 Created`

```json
{
    "data": {
        "username": "udin_petot",
        "name": "Udin Petot Jr"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `400 Bad Request`

```json
{
    "error_code": "USERNAME_TAKEN",
    "message": "Username already used"
}
```

## Login User

**Method**: POST

**Endpoint**: `/api/users`

**Request Body**:

```json
{
    "username": "udin_petot",
    "password": "rahasia"
}
```

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "username": "udin_petot",
        "name": "Udin Petot Jr",
        "token": "Bearer token"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "INVALID_CREDENTIALS",
    "message": "Username or password invalid"
}
```

## Update User

**Method**: PATCH

**Endpoint**: `/api/users/current`

**Headers**:
- `Authorization: Bearer <token>`

Request Body

```json
{
    "name": "Udin Petot Jr", //optional
    "password": "rahasia" //optional
}
```

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "username": "udin_petot",
        "name": "Udin Petot Jr"
    }
}
```

**Response Body (Failed)**:

**Status Code**: `400 Bad Request`

```json
{
    "error_code": "UPDATE_FAILED",
    "message": "Failed to update data"
}
```

## Get User

**Method**: GET

**Endpoint**: `/api/users/current`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "username": "udin_petot",
        "name": "Udin Petot Jr",
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```

## Logout User

**Method**: DELETE

**Endpoint**: `/api/users/current`

**Headers**:
- `Authorization: Bearer <token>`

**Response Body (Success)**:

**Status Code**: `200 OK`

```json
{
    "data": {
        "message": "Logout successful",
    }
}
```

**Response Body (Failed)**:

**Status Code**: `401 Unauthorized`

```json
{
    "error_code": "UNAUTHORIZED",
    "message": "Access denied. Please provide a valid Bearer token."
}
```