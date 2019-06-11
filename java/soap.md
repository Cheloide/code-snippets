

# Config Request:
```java
    PortType portType = (new Service()).getPortType();
    BindingProvider bindingProvider =  (BindingProvider) portType;

    //Set Endpoint
    bindingProvider.getRequestContext().put("javax.xml.ws.service.endpoint.address", myUrl);
    //Set Timeout (in millis), depends on jax-ws version 
    bindingProvider.getRequestContext().put("javax.xml.ws.client.receiveTimeout", 3000);
    bindingProvider.getRequestContext().put("javax.xml.ws.client.connectionTimeout", 5000);
    bindingProvider.getRequestContext().put("com.sun.xml.ws.request.timeout", 3000);
    bindingProvider.getRequestContext().put("com.sun.xml.ws.connect.timeout ", 5000);
    //timeout jdk6 (Weblogic 11)
    bindingProvider.getRequestContext().put("com.sun.xml.internal.ws.request.timeout", 10000);
    bindingProvider.getRequestContext().put("com.sun.xml.internal.ws.connect.timeout", 10000);
```