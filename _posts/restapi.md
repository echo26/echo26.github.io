# REST API

## REST
REST(Representational State Transter) is a set of architectural constraints, not a protocol or standard. Determine how API looks like.

**composition**
* Resource : URI
* Verb : HTTP Method
* Representations

## RESTful api의 조건

* Uniform Interface: Uniform Inter face between components so info is transffered in standard form.
    * resources requested !=(identicable and seperate) representations sent to the client
    * resources can be mamipulated by the client via the representation because the representation contains enough information to do so.
    * Self-descriptive message returned to the client have enough information to describe how the client should process it.
* Stateless: no state information is stored between get requests. (Not store session or cookie info. Only process incoming requests). Seperate and unconnected request.
* Cachable: Able to use existing intfra because REST use HTTP web standard. HTTP caching available.
* Layered system: orgranized in each type of server (thos responsible for security, load-balancing...) invloved the retrieval of info into hierarchies invisible to client.
* Client-server architecture: REST server provides API. client manages authorization and context (session, login info).


## Design REST API

`TWO key factors in design REST`
1. URL must describe resource of information
2. Actions for resources should be described in HTTP method (GET, POST, PUT, DELETE)

### REST API main roles

* URI should represent resource of information
```
GET /members/delete/1 (X : delete is not resource)
```

* Actions for resource should be described in HTTP method
```
DELETE /members/1 (O)
```

* example) GET User info
```
GET /members/show/1 (x)
GET /members/1 (O)
```

* exmplae) Add User
```
GET /members/insert/2 (X)
POST /members/2 (O)
```

### precautions in designing URI

* use (/) represents hierarchies
```
http://restapi.example.com/houses/apartments
http://restapi.example.com/animals/mammals/whales
```

* URI must not end up with (/)
```
http://restapi.example.com/houses/apartments/ (X)
http://restapi.example.com/houses/apartments  (0)
```

* hypen(-) for legibility

* not use underscore (_)

* URI path in small letters

* No file extension in URI

### describe relation between resources

```
GET : /users/{userid}/devices (소유의 관계를 나타낼 때)
GET : /users/{userid}/likes/devices (관계 명이 애매하거나 구체적 표현이 필요할 때)
```

### Collection & Document

* document : 문서 또는 객체. resources
* collection : set of documents resources (in plural (s)! )

```
http:// restapi.example.com/sports/soccer (collection: sports. document: soccer)
```


[link](https://meetup.toast.com/posts/92)
