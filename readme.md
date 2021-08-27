# Readme

## docs
https://robferguson.org/blog/2018/12/24/flowable-rest-api-part-1/


https://flowable.com/open-source/docs/bpmn/ch15-REST/


https://github.com/flowable/flowable-engine/issues/1471

https://forum.flowable.org/t/how-to-use-rest-api-in-docker/2977/

https://paulhh.wordpress.com/author/paulhh/

<!-- https://camunda.com/blog/2015/08/start-and-complete-process-with-rest-api/

https://docs.camunda.org/manual/7.3/api-references/rest/#process-definition-start-process-instance -->


## Url

- lx-docker03:8080/flowable-idm/#/
- lx-docker03:8888/flowable-modeler/#/
- lx-docker03:9999/flowable-task/#/


## opvragen via REST

### taken
#### check tasks
curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/runtime/tasks'


#### Curl commandos

curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/repository/deployments'

**get form ID**
curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/repository/process-definitions'

**start form processDefinitionKey**
curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/repository/process-definitions/geba_flow_rest_1:3:2f304a19-eee4-11eb-a22f-0242c0a8c005/start-form'

**start process**

curl -H "Content-Type: application/json" -X POST http://admin:test@localhost:9999/flowable-task/process-api/runtime/process-instances -d "@data-0.json"

https://gebaflow.requestcatcher.com



**get processes**
curl -i 'http://admin:test@localhost:9999/flowable-task/process-api/runtime/process-instances'
**get variables**
curl -i 'http://admin:test@localhost:9999/flowable-task/process-api/runtime/process-instances/53197106-eef0-11eb-a22f-0242c0a8c005/variables'




curl -i 'http://admin:test@0.0.0.0:9999/flowable-task/process-api/runtime/tasks/d06b0285-eee4-11eb-a22f-0242c0a8c005/form'






#### Curl Actie uitvoeren:
 
curl -H "Content-Type: application/json" 
     -X POST http://admin:test@localhost:9999/flowable-task/process-api/runtime/tasks/d7d28db2-eedf-11eb-a22f-0242c0a8c005
     -d "@data-1.json"

data-1.json
{
  "action" : "complete",
  "variables" : [
    {
        "id": "continent",
        "name": "Continent",
        "type": "dropdown",
        "value": "EU"
    },
    {
        "id": "budget",
        "name": "Budget",
        "type": "integer",
        "value": 12
    },
    {
        "id": "employeeNumber",
        "name": "Employee Number",
        "type": "integer",
        "value": 123456
    },
    {
        "id": "clientname",
        "name": "Client Name",
        "type": "text",
        "value": "Kai"
    }
  ]
}








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




