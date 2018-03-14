# rest2knx
A REST interface for KNXnet/IP

Just an idea so far, using this as a scratchpad

- Use https://github.com/h2o/picohttpparser for parsing HTTP
- Format for enpoints: /area/line/member
- GET /1/2/3/?dpt=1
  - Sends a KNX_CT_READ for GA 1/2/3, waits for answer, and return the result parsed as the given DPT, in this case a bool.
  - If no DPT is given, just return the raw data with a DPT of null
- POST /1/2/3
  - Sends a KNX_CT_WRITE for GA 1/2/3 with the posted data as data


Use JSON for GET answers and POST?

Possible GET Answer:
```json
{
  "dpt": 1,
  "rawdata": [1],
  "data": true
}
```

POST request:
```json
{
  "dpt": 1,
  "rawdata": [1]
}
```
or
```json
{
  "dpt": 1,
  "data": true
}
```
