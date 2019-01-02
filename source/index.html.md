--- 

title: traccar 

language_tabs: 
   - shell 

toc_footers: 
   - <a href='#'>Sign Up for a Developer Key</a> 
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a> 

includes: 
   - errors 

search: true 

--- 

# Introduction 

**Version:** 4.2 

# Authentication 

|basic|*Basic*|
|---|---| 

# /COMMANDS
## ***GET*** 

**Summary:** Fetch a list of Saved Commands

**Description:** Without params, it returns a list of Drivers the user has access to

### HTTP Request 
`***GET*** /commands` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Saved Command

### HTTP Request 
`***POST*** /commands` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /COMMANDS/{ID}
## ***PUT*** 

**Summary:** Update a Saved Command

### HTTP Request 
`***PUT*** /commands/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Saved Command

### HTTP Request 
`***DELETE*** /commands/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /COMMANDS/SEND
## ***GET*** 

**Summary:** Fetch a list of Saved Commands supported by Device at the moment

**Description:** Return a list of saved commands linked to Device and its groups, filtered by current Device protocol support

### HTTP Request 
`***GET*** /commands/send` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Could happen when the user doesn't have permission for the device |

## ***POST*** 

**Summary:** Dispatch commands to device

**Description:** Dispatch a new command or Saved Command if _body.id_ set

### HTTP Request 
`***POST*** /commands/send` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Command sent |
| 202 | Command queued |
| 400 | Could happen when the user doesn't have permission or an incorrect command _type_ for the device |

# /COMMANDS/TYPES
## ***GET*** 

**Summary:** Fetch a list of available Commands for the Device or all possible Commands if Device ommited

### HTTP Request 
`***GET*** /commands/types` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| deviceId | query |  | No | integer |
| textChannel | query |  | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | Could happen when trying to fetch from a device the user does not have permission |

# /DEVICES
## ***GET*** 

**Summary:** Fetch a list of Devices

**Description:** Without any params, returns a list of the user's devices

### HTTP Request 
`***GET*** /devices` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
| id | query | To fetch one or more devices. Multiple params can be passed like `id=31&id=42` | No | integer |
| uniqueId | query | To fetch one or more devices. Multiple params can be passed like `uniqueId=333331&uniqieId=44442` | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | No permission |

## ***POST*** 

**Summary:** Create a Device

### HTTP Request 
`***POST*** /devices` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /DEVICES/{ID}
## ***PUT*** 

**Summary:** Update a Device

### HTTP Request 
`***PUT*** /devices/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Device

### HTTP Request 
`***DELETE*** /devices/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /DEVICES/{ID}/ACCUMULATORS
## ***PUT*** 

**Summary:** Update total distance and hours of the Device

### HTTP Request 
`***PUT*** /devices/{id}/accumulators` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /GROUPS
## ***GET*** 

**Summary:** Fetch a list of Groups

**Description:** Without any params, returns a list of the Groups the user belongs to

### HTTP Request 
`***GET*** /groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Group

### HTTP Request 
`***POST*** /groups` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | No permission |

# /GROUPS/{ID}
## ***PUT*** 

**Summary:** Update a Group

### HTTP Request 
`***PUT*** /groups/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Group

### HTTP Request 
`***DELETE*** /groups/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /PERMISSIONS
## ***POST*** 

**Summary:** Link an Object to another Object

### HTTP Request 
`***POST*** /permissions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | No permission |

## ***DELETE*** 

**Summary:** Unlink an Object from another Object

### HTTP Request 
`***DELETE*** /permissions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /POSITIONS
## ***GET*** 

**Summary:** Fetches a list of Positions

**Description:** Without any params, it returns a list of last known positions for all the user's Devices. _from_ and _to_ fields are not required with _id_

### HTTP Request 
`***GET*** /positions` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| deviceId | query | _deviceId_ is optional, but requires the _from_ and _to_ parameters when used | No | integer |
| from | query | in IS0 8601 format. eg. `1963-11-22T18:30:00Z` | No | dateTime |
| to | query | in IS0 8601 format. eg. `1963-11-22T18:30:00Z` | No | dateTime |
| id | query | To fetch one or more positions. Multiple params can be passed like `id=31&id=42` | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /SERVER
## ***GET*** 

**Summary:** Fetch Server information

### HTTP Request 
`***GET*** /server` 

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***PUT*** 

**Summary:** Update Server information

### HTTP Request 
`***PUT*** /server` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /SESSION
## ***GET*** 

**Summary:** Fetch Session information

### HTTP Request 
`***GET*** /session` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| token | query |  | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 404 | Not Found |

## ***POST*** 

**Summary:** Create a new Session

### HTTP Request 
`***POST*** /session` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| email | formData |  | Yes | string |
| password | formData |  | Yes | password |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 401 | Unauthorized |

## ***DELETE*** 

**Summary:** Close the Session

### HTTP Request 
`***DELETE*** /session` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /USERS
## ***GET*** 

**Summary:** Fetch a list of Users

### HTTP Request 
`***GET*** /users` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| userId | query | Can only be used by admin or manager users | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |
| 400 | No Permission |

## ***POST*** 

**Summary:** Create a User

### HTTP Request 
`***POST*** /users` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /USERS/{ID}
## ***PUT*** 

**Summary:** Update a User

### HTTP Request 
`***PUT*** /users/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a User

### HTTP Request 
`***DELETE*** /users/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /NOTIFICATIONS
## ***GET*** 

**Summary:** Fetch a list of Notifications

**Description:** Without params, it returns a list of Notifications the user has access to

### HTTP Request 
`***GET*** /notifications` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Notification

### HTTP Request 
`***POST*** /notifications` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /NOTIFICATIONS/{ID}
## ***PUT*** 

**Summary:** Update a Notification

### HTTP Request 
`***PUT*** /notifications/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Notification

### HTTP Request 
`***DELETE*** /notifications/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /NOTIFICATIONS/TYPES
## ***GET*** 

**Summary:** Fetch a list of available Notification types

### HTTP Request 
`***GET*** /notifications/types` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /NOTIFICATIONS/TEST
## ***POST*** 

**Summary:** Send test notification to current user via Email and SMS

### HTTP Request 
`***POST*** /notifications/test` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | Successful sending |
| 400 | Could happen if sending has failed |

# /GEOFENCES
## ***GET*** 

**Summary:** Fetch a list of Geofences

**Description:** Without params, it returns a list of Geofences the user has access to

### HTTP Request 
`***GET*** /geofences` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Geofence

### HTTP Request 
`***POST*** /geofences` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /GEOFENCES/{ID}
## ***PUT*** 

**Summary:** Update a Geofence

### HTTP Request 
`***PUT*** /geofences/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Geofence

### HTTP Request 
`***DELETE*** /geofences/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /EVENTS/{ID}
## ***GET*** 

### HTTP Request 
`***GET*** /events/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /REPORTS/ROUTE
## ***GET*** 

**Summary:** Fetch a list of Positions within the time period for the Devices or Groups

**Description:** At least one _deviceId_ or one _groupId_ must be passed

### HTTP Request 
`***GET*** /reports/route` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /REPORTS/EVENTS
## ***GET*** 

**Summary:** Fetch a list of Events within the time period for the Devices or Groups

**Description:** At least one _deviceId_ or one _groupId_ must be passed

### HTTP Request 
`***GET*** /reports/events` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
| type | query | % can be used to return events of all types | No | array |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /REPORTS/SUMMARY
## ***GET*** 

**Summary:** Fetch a list of ReportSummary within the time period for the Devices or Groups

**Description:** At least one _deviceId_ or one _groupId_ must be passed

### HTTP Request 
`***GET*** /reports/summary` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /REPORTS/TRIPS
## ***GET*** 

**Summary:** Fetch a list of ReportTrips within the time period for the Devices or Groups

**Description:** At least one _deviceId_ or one _groupId_ must be passed

### HTTP Request 
`***GET*** /reports/trips` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /REPORTS/STOPS
## ***GET*** 

**Summary:** Fetch a list of ReportStops within the time period for the Devices or Groups

**Description:** At least one _deviceId_ or one _groupId_ must be passed

### HTTP Request 
`***GET*** /reports/stops` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /STATISTICS
## ***GET*** 

**Summary:** Fetch server Statistics

### HTTP Request 
`***GET*** /statistics` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /CALENDARS
## ***GET*** 

**Summary:** Fetch a list of Calendars

**Description:** Without params, it returns a list of Calendars the user has access to

### HTTP Request 
`***GET*** /calendars` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Calendar

### HTTP Request 
`***POST*** /calendars` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /CALENDARS/{ID}
## ***PUT*** 

**Summary:** Update a Calendar

### HTTP Request 
`***PUT*** /calendars/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Calendar

### HTTP Request 
`***DELETE*** /calendars/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /ATTRIBUTES/COMPUTED
## ***GET*** 

**Summary:** Fetch a list of Attributes

**Description:** Without params, it returns a list of Attributes the user has access to

### HTTP Request 
`***GET*** /attributes/computed` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create an Attribute

### HTTP Request 
`***POST*** /attributes/computed` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /ATTRIBUTES/COMPUTED/{ID}
## ***PUT*** 

**Summary:** Update an Attribute

### HTTP Request 
`***PUT*** /attributes/computed/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete an Attribute

### HTTP Request 
`***DELETE*** /attributes/computed/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /DRIVERS
## ***GET*** 

**Summary:** Fetch a list of Drivers

**Description:** Without params, it returns a list of Drivers the user has access to

### HTTP Request 
`***GET*** /drivers` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Driver

### HTTP Request 
`***POST*** /drivers` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /DRIVERS/{ID}
## ***PUT*** 

**Summary:** Update a Driver

### HTTP Request 
`***PUT*** /drivers/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Driver

### HTTP Request 
`***DELETE*** /drivers/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

# /MAINTENANCE
## ***GET*** 

**Summary:** Fetch a list of Maintenance

**Description:** Without params, it returns a list of Maintenance the user has access to

### HTTP Request 
`***GET*** /maintenance` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***POST*** 

**Summary:** Create a Maintenance

### HTTP Request 
`***POST*** /maintenance` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

# /MAINTENANCE/{ID}
## ***PUT*** 

**Summary:** Update a Maintenance

### HTTP Request 
`***PUT*** /maintenance/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | OK |

## ***DELETE*** 

**Summary:** Delete a Maintenance

### HTTP Request 
`***DELETE*** /maintenance/{id}` 

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
|  |  |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 204 | No Content |

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
