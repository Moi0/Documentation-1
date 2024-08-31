# Froxlor

## Froxlor.checkUpdate

checks whether there is a newer version of froxlor available

#### Permission

`admin`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| force | bool | optional, force live update-check |

#### Response

`string` as `json-encoded array`

## Froxlor.importSettings

import settings

#### Permission

`admin`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| json_str | string | content of exported froxlor-settings json file |

#### Response

`string` as `json-encoded bool`

## Froxlor.exportSettings

export settings

#### Permission

`admin`

#### Response

`string` as `json-string`

## Froxlor.listSettings

return a list of all settings

#### Permission

`admin`

#### Response

`string` as `json-encoded array count|list`

## Froxlor.getSetting

return a setting by settinggroup.varname couple

#### Permission

`admin`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| key | string | settinggroup.varname couple |

#### Response

`string`

## Froxlor.updateSetting

updates a setting

#### Permission

`admin`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| key | string | settinggroup.varname couple |
| value | string | optional the new value, default is '' |

#### Response

`string`

## Froxlor.generatePassword

returns a random password based on froxlor settings for min-length, included characters, etc.

#### Permission

`admin` `customer`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| length | int | optional length of password, defaults to 0 (panel.password_min_length) |

#### Response

`string`

## Froxlor.generateLoginLink

return a one-time login link URL for a given user

#### Permission

`admin`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| loginname | int $customerid optional, required if | is not specified, user to create link for |
| customerid | string $loginname optional, required if | is not specified, user to create link for |
| valid_time | int | optional, value in seconds how long the link will be valid, default is 10 seconds, valid values are numbers from 10 to 120 |
| allowed_from | string | optional, comma separated list of ip addresses or networks to allow login from via this link |

#### Response

`string` as `json-encoded array [base => domain, uri => relative link]`

## Froxlor.integrityCheck

can be used to remotely run the integritiy checks froxlor implements

#### Permission

`admin`

#### Response

`string`

## Froxlor.listFunctions

returns a list of all available api functions

#### Permission

`admin` `customer`

#### Parameter

| Field | Type | Description |
| :--- | :--- | :--- |
| module | string | optional, return list of functions for a specific module |
| function | string | optional, return parameter information for a specific module and function |

#### Response

`string` as `json-encoded array`