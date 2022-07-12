# Dig:T integrations using Camunda

The [Camunda platform](https://camunda.com/platform/) is a modular process orchestrator that can  xxxxxx.

Although it's main field might not be to be used as a "simple" [integration platform](https://en.wikipedia.org/wiki/Integration_platform), it works really well as such. It contains all the neccessary bells and whistles that one would need from an integration platform, like process orchestration, load balancing, error handling and monitoring.


**However, the use of Digi:T's Camunda platform as an integration platform shall only be used to integrate Digi:T's e-services with backend systems. No other usage is supported.**


## Architecture principals

## Components

### Camunda wrapper
The Camunda wrapper wrapps the [Zeebe engine](https://docs.camunda.io/docs/components/zeebe/technical-concepts/architecture/) (e.g. the Zeebe gateway) and provides a flexible but minimalistic REST-interface. It also provides a JWT-based authentication scheme. The same wrapper is used to start "normal" processes, catch Epi-forms posts and provide an interface to the Operator component. These functions are described elsewhere.

The URL for the integrations are
```
https://camunda-wrapper.<environment>.digit.haninge.se/integration/<integration name>?<request parameters>
```

The HTTP-method is always a GET. Other methods are not supported. The result is returned as a JSON-structure with the "content-type" set to "application/json". The actual content is a contract between the caller and the actual integration.




### Zeebe engine (BPMN processor)

### Intregrations (workers)

All integrations are implemented as "workers" to the [Zeebe engine](https://docs.camunda.io/docs/components/zeebe/technical-concepts/architecture/) and follow a fix communication protocol. And can thus be written in any language.
