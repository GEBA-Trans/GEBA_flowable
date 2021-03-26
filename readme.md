# Readme

## docs
https://robferguson.org/blog/2018/12/24/flowable-rest-api-part-1/


https://flowable.com/open-source/docs/bpmn/ch15-REST/


https://github.com/flowable/flowable-engine/issues/1471



## opvragen via REST

### taken
#### check tasks
curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/runtime/tasks'


#### Curl commandos

curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/repository/deployments'

curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/repository/process-definitions'

curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/runtime/process-instances'
curl -i 'http://admin:test@localhost:9999/flowable-task/process-api/runtime/tasks'

#### Curl Actie uitvoeren:
 
curl -H "Content-Type: application/json" 
     -X POST http://admin:test@localhost:8080/flowable-task/process-api/runtime/tasks/1fae489a-070f-11e9-a85e-0242ac110002
     -d "@data-1.json"

data-1.json
{
  "action" : "complete",
  "variables" : [
    {
        "id": "givenName",
        "name": "Given Name",
        "type": "string",
        "value": "Rob"
    },
    {
        "id": "familyName",
        "name": "Family Name",
        "type": "string",
        "value": "Ferguson"
    },
    {
        "id": "employeeNumber",
        "name": "Employee Number",
        "type": "integer",
        "value": 123456
    },
    {
        "id": "fromDate",
        "name": "From Date",
        "type": "date",
        "value": "2018-12-21T00:00:00+00:00"
    },
    {
        "id": "toDate",
        "name": "To Date",
        "type": "date",
        "value": "2019-01-07T00:00:00+00:00"
    }
  ]
}
