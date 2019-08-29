# win32-api-service
Windows LoadLibrary + GetProcAddress + function invocation as a service

## POST /library/load

Request

```json
{
  "path": ""C:\\Windows\\System32\\dsdevice-original.dll""
}
```

Response

```json
{
  "address": 0x11223344
}
```

## GET /library/:hDllAddress/function/:functionName/address

Response

```json
{
  "address": 0x11223344
}
```

## POST /library/:hDllAddress/function/:address/call

```json
{
  "arguments": [
    {"type": "int", "value": 1},
    {"type": "char*", "value": "Hello, world!"},
    {"type": "void*", "value": 0x1122334}
  ]
}
```

Response

```json
{
  "result": 1
}
```json
