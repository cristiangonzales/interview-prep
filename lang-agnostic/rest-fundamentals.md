RESTful Fundamentals
---

### Definition of REST
> Architectural style for designing loosely coupled applications over HTTP

### Guiding Principles of REST––What makes a service *RESTful*?
1. Client-server
  * Improve UI portability across platforms and server scalability
2. Stateless
  * Session state kept entirely by the client, not dependent on the server
3. Cacheable
  * Responses must be labeled as cacheable or noncacheable (if cacheable, cached information can be used in subsequent events)
4. Uniform interface
  * Identification of resources
  * Manipulation of resources through representations
  * Self-descriptive messages
  * Hypermedia as the engine of application state (HATEOAS)
5. Layered system
  * Each component cannot "see" beyond the immediate layer they are interacting with
6. Code on demand
  * Download/execute code in the form of applet/scripts

##### Resource
* Any information that can be named is a resource
* Resource identifier
* *Resource representation*: state of resource of any particular timestamp
* *Media type*: data format of a representation
* A truly RESTful API looks like hypertext
  * *Hypertext*: simultaneous presentation of information and controls
* Resource representations shall be self-descriptive
* Every media type defines a defualt processing model

##### Resource Methods
* Fielding doesn't mention `PUT`/`POST`/`GET` methods specifically, just says that the methods being used should be uniform-interface
* Query based API results should be represented by a list of links with summary information

##### REST ≠ HTTP
* Fielding never mentioned implementation/protocol specifics
* In REST, resources are accessed via URIs (Uniform Resource Identifier)
* Resources are decoupled from representation so content can be accessed in a variety of formats

---

### REST Resource Naming Guide
* Resource can be a singleton or a collection
  * `/customers/{customerId}`
* Resource may contain subcollection resources
  * `/customers/{customerId}/accounts/{accountId}`
* Best practices: Use nouns to represent resources
  * Always target to put a resource into one archetype and use its naming convention consistently
    1. document (singular––object instance)
    2. collection (plural––directory of resources)
    3. store (plural––client managed resource repository)
    4. controller (verb––procedural concept)
* Best practices: Consistency is the key
  * Use forward slash (`/`) to indicate hierarchical relationships
  * Do not use trailing forward slashes in URIs
  * Use hyphens to improve readability of URIs
  * Do not use underscores as seperators
  * Use lowercase letters in URI
  * Do not use file extensions
* Best practices: Never use CRUD function names in URIs (instead, HTTP request methods should be used to indicate which CRUD function is performed)
* Best practices: Use query component to filter URI collection (query parameters)
* REST Versus CRUD (Create, Read, Update, Delete)
  * CRUD => set primitive operations for databases and static data storages
  * REST => high-level API style for web services and live systems
* Solving the *N + 1 problem* (for N requests): include more information in individual resources inside collection resources

---
### REST API Caching Response
* Origin server indicates whether a response can be cached (by who and how long)
  * Caches can cache a fresh copy if allowed
* Quality of Service
  * Reduce bandwidth
  * Reduce latency
  * Reduce load on servers
  * Hide network failures
* `GET` requests should be cacheable by default
  * `PUT`s and `DELETE`s are not cacheable at all
* HTTP response headers
  * Expires
  * Cache-control
  * ETag (identifies stage of resource)
  * Last-Modified

---
### REST Resource Representation Compression
* Different protocols use different techniques to enable compression
* Accept-Encoding (Client request)
  * `compress` and `gzip`
* Content-Encoding (Server response)

---
### REST – Content Negotiation
* Definition: Client asking server for a suitable presentation
* Server-driven VS Agent-driven Content Negotiation
  * Not much use for server-driven becuase you would make lots of assumptions on client expectations
* Content negotiation using HTTP headers
  * To determine entity of request, server uses `Content-Type`
  * Client uses `Accept` to identify desired type
* Content negotiation using URL patterns (use specific extension in URI)

---
### HATEOAS
* *HATEOAS*: Hypermedia as the Engine of Application State
  * Hypermedia refers to context that contains links to other forms of media
  * Hypermedia links returned from the server drive the application's state and not the other way around
* HATEOAS Implementation
  * REST client hits an initial API URI and uses the server-provided links to dynamically discover available actions and access the resources it needs
  * Clients no longer have to hard code the URI structures for different resources
* Formats for specifying JSON REST API hypermedia links
  * RFC 5988 (web linking)
    * Target IRI (Internationalized Resource Identifiers) (`href`)
    * Link relation type (describes how current context is related to target resource) (`rel`)
    * Attributes for target IRI
  * JSON Hypermedia API Language
    * JSON/XML
    * Target URI, Link relation, Type

---
### Idempotency
* *Idempotent API*: making identical requests have the same effect as making a single request
* Design fault-tolerant APIs where duplicate requests do not break the system
* `POST` => **not** idempotent (creating new resource with every request)
* `PUT` => subsequent requests will just overwrite the same resource over and over again (is idempotent)
* `DELETE` => subsequent requests will not change state because the first request already deleted the first resource (is idempotent)
* `GET` is idempotent (never changes state)

---
### REST API Security
* REST Security Design Priciples
  * Least privilege
    * Only give required permissions to perform actions for which they were authorized
  * Fail-Safe Defaults
    * Default access level: "denied"
  * Economy of Mechanism
    * Interfaces should be simple enough to understand
  * Complete Mediation
    * System should validate access rights and not rely on cached permission matrix
  * Open design
    * No secret, confidential algorithms
  * Seperation of Privileges
    * Granting permissions should not be based on a single condition
  * Least Common Mechanism
    * Sharing state among different components => dependent components can become corrupt
  * Psychological Acceptability
    * Security should not make UX worse
* REST API Best Practices
  * Keep it simple
  * Always use HTTPS
  * Use password hash
  * Never expose information on URLs (user/password session tokens, API keys)
  * OAuth 2.0
    * Limited access to HTTP service on behalf of a resource owner or allowing a 3rd party app access on its own behalf
  * Consider Adding Timestamp in Request
    * Server only accepts requests within a reasonable timestamp (1-2 minutes) (prevents brute force attacks)
  * Input Parameter Validation
    * Validate request parameters before it reaches application logic

---
### API Versioning
* Breaking changes
  * Change in format of response data
  * Change in response type
  * Removing any part of the API
* URI Versioning
  * Break client integration
* Versioning using Custom Request Header
* Versioning using Accept header
  * End result: more complex API, API controllers have to decide which version of a resource to send

---
### Statelessness
* *Statelessness*: Server does not store any state about client session
* Client responsible for storing application state
  * No sticky sessions
  * Every HTTP request happens in isolation
* *Application state*: server side data regarding previous interaction details with client (this is not OK for REST)
* *Resource state*: Current state of a resource on a server (this is OK for rest)
* Advantages
  * Helps to scale APIs (no session related dependency)
  * Makes REST APIs less complex
  * Easy to cache (no uncertainty about application state affecting cacheability)
  * Server never loses track of "where" a client is in the application

---
### HTTP Status Codes
* `1xx`: Informational (transfer protocol-level information)
* `2xx`: Success
  * `200` OK
  * `201` Created
  * `202` Accepted
  * `204` No Content
* `3xx`: Redirection (client must take additional action)
  * `301` Moved Permanently
  * `302` Found
  * `303` See Other
  * `304` Not Modified
  * `307` Temporary Redirect
* `4xx`: Client Error
  * `400` Bad Request
  * `401` Unauthorized
  * `403` Forbidden
  * `404` Not Found
  * `405` Method Not Allowed
  * `406` Not Acceptable
  * `412` Precondition Failed
  * `415` Unsupported Media Type
* `5xx`: Server Error
  * `500` Internal Server Error
  * `501` Not Supported

---
### HTTP Methods
* `GET`: retrieve resource representation/information only
  * Status codes: `200`, `404`, `400`
* `POST`: create new subordinate resources; create a new resource into a collection of resources
  * Status codes: `201`, `200`, `204`
* `PUT`: update existing resources
  * Status codes: `201`, `200`, `204`
* `DELETE`: delete resources
  * Status codes: `200`, `202`, `204`
