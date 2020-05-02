
- [Models](#models)
  * [A2E Response](#a2e-response)
  * [User](#user)
  * [Final Response](#final-response)
  * [A2E Request](#a2e-request)
- [Endpoints](#endpoints)
  * [SignUp request](#signup-request)
  * [OTP verification](#otp-verification)
  * [Save Password](#save-password)
  * [Login](#login)


## Models

### A2E Response

```ts
{
  "respCode" :<int>,
  "subRespCode":<int>,
  "respMsg":<String>,
}
```

## User
```ts
{
  "id" :<long>,
  "firstName" : <String>,
  "lastName": <String>,
  "email": <String>,
  "phone": <String>,
  "whatsapp":<String>,
  "slack":<String>,
  "isActive":<Boolean>,
  "uniqueCodeExpiration":<Date>,
  "isProspect" : <Boolean>,
  "updatedOn": <Date>,
  "lastLogin":<Date,
  "createdOn": <Date>
}
```

## Final Response
```ts
{
  "finalResp" : <A2E Response>,
  "details":<User>
}
```

### A2E Request
```ts
"callerInfo": {
       "appName": "Collaboration",
       "appKey" : "12345"// use these temporary values till we implement proper authorization technique.
     }
```

## Endpoints

### SignUp Request

```ts
POST "/signup"
HEADERS {
  "Content-Type" : "application/json"
}
```

##### Request body
```ts
    {
      "callerInfo": {
             "appName": "Collaboration",
             "appKey" : "12345"// use these temporary values till we implement proper authorization technique.
           },
      "user":{
        "isProspect": <Boolean>,
        "email" : <String>,
        "firstName": <String>,
        "lastName": <String>
      }
    }

```

##### Response body
```ts
 <Final response>
```

### OTP Verification
```ts
POST "/signup/otp"
HEADERS {
  "Content-Type" : "application/json"
}
```
##### Request body
```ts

{
  "callerInfo": {
         "appName": "Collaboration",
         "appKey" : "12345"// use these temporary values till we implement proper authorization technique.
       },
  "user"{
    "email":<String>,
    "secret":{
      "otp" : <String>
    }
  }
}
```

##### Response body
```ts
  <Final response>
```

### Save Password
```ts
POST "/sigup/password"
HEADERS {
  "Content-Type" : "application/json"
}
```
##### Request body
```ts
{
  "callerInfo": {
         "appName": "Collaboration",
         "appKey" : "12345"// use these temporary values till we implement proper authorization technique.
       },
  "user"{
    "email":<String>,
    "secret":{
      "password" : <String>
    }
  }
}
```

##### Response body
```ts
  <Final response>
```
## Login
```ts
POST "/login"
HEADERS {
  "Content-Type" : "application/json"
}
```
#### Request body
```ts
{
  "callerInfo": {
         "appName": "Collaboration",
         "appKey" : "12345"// use these temporary values till we implement proper authorization technique.
       },
  "login":{
         "email":<String>,
         "password":<String>
  }
}

```
#### Response body
```ts
  <Final response>
```

##### Additonal into
```ts

```
