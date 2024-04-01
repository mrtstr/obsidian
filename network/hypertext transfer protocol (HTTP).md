## hypertext transfer protocol (HTTP)
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
-  extendable headers
- default [[port]] is TCP 80, but other ports can be used

### steps
1) establishement of [[transmission control protocol (TCP)|TCP connection]]
2) [[client]] sends a **request** to the [[server]]
3) [[server]] answers with a **response**
	- Request ([[client]] to [[server]])
	- Response ([[server]] to [[client]])
4) reusing or closing of [[transmission control protocol (TCP)|TCP connection]]

### [[statefulness of protocols|statefulness]]
- [[hypertext transfer protocol (HTTP)]] is [[statefulness of protocols|stateless]]
- statefulness can be achived with HTTP cookies

![[statefulness of protocols#statefulness of protocols]]

### requirments for [[transport layer]] [[protocol]]
- reliable (which [[transmission control protocol (TCP)]] is but [[user datagram protocol (UDP)]] is not)
- does not need to be [[statefulness of protocols|stateful]] and connection based
	→ almost always used on top of [[transmission control protocol (TCP)]] 

### relationship of http versions to underlaying protocols
- versions 1.0 ro 2.0 are based on [[transmission control protocol (TCP)]] while HTTP/3 uses the [[user datagram protocol (UDP)]] based [[QUIC]]
#### HTTP/1.0
- one [[transmission control protocol (TCP)|TCP connection]] per request/response pair which is inefficient
#### HTTP/1.1
- possible to execute several requests using a [[transmission control protocol (TCP)|TCP connection]] with `keep-alive` option
- added pipelining: multiple requests can be sent before an answer arrived as long the order of responses matched the order of requests but this created problems and was removed
#### HTTP/2
- multiple requests can be sent at the same time over independent streams over a single [[transmission control protocol (TCP)|tcp connections]] → eliminates the oout-of-orderproblem of HTTP/1.1
- added push option to update when new data is avalibale

#### HTTP/3
- uses [[QUIC]] which is on top of [[user datagram protocol (UDP)]] instead of [[transmission control protocol (TCP)]]
- optimized for mobile applications because when the mobile network is swiched the [[transmission control protocol (TCP)|TCP connection]] has to be reestablished
- with [[QUIC]] the stream session can be reused

![[transmission control protocol (TCP)#TCP connection]]

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```

#### HEAD
- similar to **GET**, but the response should have just the header
- for example to check the `Content-Length` of a potentially lage file before downloading
- idempotent

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

#### DELETE
- request to deletes the specified resource
- idempotent

#### CONNECT
- starts two-way communications with the requested resource
- can be used to open a tunnel

#### OPTIONS
- requests permitted communication options for a given URL or server
- client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server

#### TRACE
- message loop-back test along the path to the target resource, providing a useful debugging mechanism



## packet structure
### first line
#### request line
```
<method> <identifier of ressource> <HTTP version>
GET /infotext.html HTTP/1.1
```
#### status line (response)
```
<HTTP version> <status code> <text explaining the status code>
HTTP/1.1 200 OK
```

### header
- contrains meta information
- line break seperated `key: value` pairs

#### request header
- `Host:` [[network domain]]
- `User-Agent:` [[client]] reviels information about himself like OS, browser
- `Referer:` previously accessed [[uniform resource locator (URL)]]
- `Content-Length:` content length in byte
- `Content-Type:` [[internet media (MIME) type]] of the data in the body

#### response header
- `Date:` date and time on the [[server]]
- `Server:` properties of the [[server]]
- `Content-Type:` [[internet media (MIME) type]] of the data in the body

![[internet media (MIME) type#internet media (MIME) type]]

### body
- transmitted data bytes
- optional
- will allways be processed but is ignored for some http methods


# anki

START
Basic
structure of a [[hypertext transfer protocol (HTTP)]] packet
Back: 
## packet structure
### first line
#### request line
```
<method> <identifier of ressource> <HTTP version>
GET /infotext.html HTTP/1.1
```
#### status line (response)
```
<HTTP version> <status code> <text explaining the status code>
HTTP/1.1 200 OK
```

### header
- contrains meta information
- line break seperated `key: value` pairs

#### request header
- `Host:` [[network domain]]
- `User-Agent:` [[client]] reviels information about himself like OS, browser
- `Referer:` previously accessed [[uniform resource locator (URL)]]
- `Content-Length:` content length in byte

#### response header
- `Date:` date and time on the [[server]]
- `Server:` properties of the [[server]]
- `Content-Type:` [[internet media (MIME) type]] of the data in the body


### body
- transmitted data bytes
- optional
- will allways be processed but is ignored for some http methods

___________________________
### [[internet media (MIME) type]]
- standardized identifier for transmitted file formats ([[hypertext transfer protocol (HTTP)]])
- consists of a type and subtypes
```
<type>/<dot seperated subtypes>
```
#### types
-   _application_ 
	- binary data that will be executed or interpreted
	- binary data that requires a specific application to use it
	- e.g. `application/json`, `application/sql`
-   _audio_ – audio files
-   _image_ – for images
-   _multipart_ – multipart file
-   _text_ 
	- any human-readable content
	- source code
	- textual data
	- e.g. `text/csv`, `text/html`, `text/javascript`, `text/xml`, `text/plain`
-   _video_ – video files

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```

#### HEAD
- similar to **GET**, but the response should have just the header
- for example to check the `Content-Length` of a potentially lage file before downloading
- idempotent

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

#### DELETE
- request to deletes the specified resource
- idempotent

#### CONNECT
- starts two-way communications with the requested resource
- can be used to open a tunnel

#### OPTIONS
- requests permitted communication options for a given URL or server
- client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server
- server response can include allowed header fields and defined methods for a ressource

#### TRACE
- message loop-back test along the path to the target resource, providing a useful debugging mechanism

Tags: code network
<!--ID: 1711907290194-->
END


START
Basic
[[hypertext transfer protocol (HTTP)]]
- summary (3)
- steps for interaction
- [[statefulness of protocols|statefulness]]
- http vesions and relationships with other protocols
Back: 
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

### steps
1) establishement of [[transmission control protocol (TCP)|TCP connection]]
2) [[client]] sends a **request** to the [[server]]
3) [[server]] answers with a **response**
	- Request ([[client]] to [[server]])
	- Response ([[server]] to [[client]])
4) reusing or closing of [[transmission control protocol (TCP)|TCP connection]]

### [[statefulness of protocols|statefulness]]
- [[hypertext transfer protocol (HTTP)]] is [[statefulness of protocols|stateless]]
- statefulness can be achived with HTTP cookies

### statefulness of protocols
#### stateful [[protocol]]
- [[server]] and the [[client]] maintain information about the state of the connection e.g. sequence numbers, number of bytes sent/recived
- e.g [[transmission control protocol (TCP)]], [[li socket]]

#### stateless [[protocol]]
- each packet is treated as an independent unit of data and the server does not maintain any information about previous packets
- typically used for simple, one-time interactions
- e.g [[hypertext transfer protocol (HTTP)]], [[internet protocol (IP)]]

### requirments for [[transport layer]] [[protocol]]
- reliable (which [[transmission control protocol (TCP)]] is but [[user datagram protocol (UDP)]] is not)
- does not need to be [[statefulness of protocols|stateful]] and connection based
	→ almost always used on top of [[transmission control protocol (TCP)]] 

### relationship of http versions to underlaying protocols
- versions 1.0 ro 2.0 are based on [[transmission control protocol (TCP)]] while HTTP/3 uses the [[user datagram protocol (UDP)]] based [[QUIC]]
#### HTTP/1.0
- one [[transmission control protocol (TCP)|TCP connection]] per request/response pair which is inefficient
#### HTTP/1.1
- possible to execute several requests using a [[transmission control protocol (TCP)|TCP connection]] with `keep-alive` option
- added pipelining: multiple requests can be sent before an answer arrived as long the order of responses matched the order of requests but this created problems and was removed
#### HTTP/2
- multiple requests can be sent at the same time over independent streams over a single [[transmission control protocol (TCP)|tcp connections]] → eliminates the oout-of-orderproblem of HTTP/1.1
- added push option to update when new data is avalibale

#### HTTP/3
- uses [[QUIC]] which is on top of [[user datagram protocol (UDP)]] instead of [[transmission control protocol (TCP)]]
- optimized for mobile applications because when the mobile network is swiched the [[transmission control protocol (TCP)|TCP connection]] has to be reestablished
- with [[QUIC]] the stream session can be reused

#### TCP connection
- [[transmission control protocol (TCP)|TCP]] connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

Tags: code network
<!--ID: 1711907290198-->
END


START
Basic
[[hypertext transfer protocol (HTTP)]]
- what is in the first line of a request/response?
- how is the header strcutures? name 3 + 3 examples for header fields.
- what kind of data is in the body, and how does the application know how to process it?
Back: 
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

## packet structure
### first line
#### request line
```
<method> <identifier of ressource> <HTTP version>
GET /infotext.html HTTP/1.1
```
#### status line (response)
```
<HTTP version> <status code> <text explaining the status code>
HTTP/1.1 200 OK
```

### header
- contrains meta information
- line break seperated `key: value` pairs

#### request header
- `Host:` [[network domain]]
- `User-Agent:` [[client]] reviels information about himself like OS, browser
- `Referer:` previously accessed [[uniform resource locator (URL)]]

#### response header
- `Date:` date and time on the [[server]]
- `Server:` properties of the [[server]]
- `Content-Type:` [[internet media (MIME) type]] of the data in the body


### body
- transmitted data bytes
- optional
- will allways be processed but is ignored for some http methods

___________________________
### [[internet media (MIME) type]]
- standardized identifier for transmitted file formats ([[hypertext transfer protocol (HTTP)]])
- consists of a type and subtypes
```
<type>/<dot seperated subtypes>
```
#### types
-   _application_ 
	- binary data that will be executed or interpreted
	- binary data that requires a specific application to use it
	- e.g. `application/json`, `application/sql`
-   _audio_ – audio files
-   _image_ – for images
-   _multipart_ – multipart file
-   _text_ 
	- any human-readable content
	- source code
	- textual data
	- e.g. `text/csv`, `text/html`, `text/javascript`, `text/xml`, `text/plain`
-   _video_ – video files

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```

#### HEAD
- similar to **GET**, but the response should have just the header
- for example to check the `Content-Length` of a potentially lage file before downloading
- idempotent

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

#### DELETE
- request to deletes the specified resource
- idempotent

#### CONNECT
- starts two-way communications with the requested resource
- can be used to open a tunnel

#### OPTIONS
- requests permitted communication options for a given URL or server
- client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server
- server response can include allowed header fields and defined methods for a ressource

#### TRACE
- message loop-back test along the path to the target resource, providing a useful debugging mechanism
Tags: code network
<!--ID: 1711907290201-->
END


START
Basic
- 9 [[hypertext transfer protocol (HTTP)]] request methods
- what are they doing?
Back: 
### [[hypertext transfer protocol (HTTP)]]
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```

#### HEAD
- similar to **GET**, but the response should have just the header
- for example to check the `Content-Length` of a potentially lage file before downloading
- idempotent

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

#### DELETE
- request to deletes the specified resource
- idempotent

#### CONNECT
- starts two-way communications with the requested resource
- can be used to open a tunnel

#### OPTIONS
- requests permitted communication options for a given URL or server
- client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server
- server response can include allowed header fields and defined methods for a ressource

#### TRACE
- message loop-back test along the path to the target resource, providing a useful debugging mechanism
Tags: code network
<!--ID: 1711907290204-->
END


START
Basic
[[hypertext transfer protocol (HTTP)]] 
- difference between `POST`, `PUT` amd `PATCH`

Back: 
`PATCH` is a partial transformation based on instrutions and is not idempotent
`PUT` is a complete replacement with the content given in the body and is idempotent with no side effect on other ressource: e.g. replacing a text file
`POST` is a request to process the given data and is not idempotent: e.g. palcing an order

### [[hypertext transfer protocol (HTTP)]]
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

### methods

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

Tags: code network
<!--ID: 1711966763605-->
END


START
Basic
[[hypertext transfer protocol (HTTP)]]
- how to check the size of a file before downloading it?
- what are `CONNECT`, `OPTION` and `TRACE` doing?
Back: 
### [[hypertext transfer protocol (HTTP)]]
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

### methods

#### GET
- request a ressource from a [[server]] with a [[uniform resource locator (URL)]]
- should only retrieve data and should not have any other effect
- all transmitted data are part of the [[uniform resource locator (URL)]]
- there can be a request body, but it will be ignored
- cachable
- idempotent

example request:
```
GET /infotext.html HTTP/1.1 # method path version
Host: www.example.net       # domain name
```

response example:
```
HTTP/1.1 200 OK    # version and status code
Server: Apache/1.3.29 (Unix) PHP/4.3.4  
Content-Length: 123456  
Content-Language: de
Connection: close
Content-Type: text/html
(request bode: html file)
```

#### HEAD
- similar to **GET**, but the response should have just the header
- for example to check the `Content-Length` of a potentially lage file before downloading
- idempotent

#### POST
- send data to a [[server]] for processing
- data is transmitted in the body and `Content-Type` field in the header specifies the content type
- not idempotent e.g. placing an order

#### PUT
- creates a new resource or replaces a representation of the target resource with the request payload.
- idempotent and no side effect on other ressources

#### PATCH
- applies partial modifications to a resource
- considered a set of instructions on how to modify a resource (unlike `PUT` which is a replacement)
- not nessarily idempotent but can be
- _may_ have side effects on other resources

#### DELETE
- request to deletes the specified resource
- idempotent

#### CONNECT
- starts two-way communications with the requested resource
- can be used to open a tunnel

#### OPTIONS
- requests permitted communication options for a given URL or server
- client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server
- server response can include allowed header fields and defined methods for a ressource
#### TRACE
- message loop-back test along the path to the target resource, providing a useful debugging mechanism
Tags: code network
<!--ID: 1711966763610-->
END

START
Basic
[[hypertext transfer protocol (HTTP)]]
- diffrent http versions and relationship with other protocols
- [[protocol]] used
- establishemt of connections
Back: 
## [[hypertext transfer protocol (HTTP)]]
-  simple and human-readable [[protocol]] in the [[application layer]] for transmitting data 
- interactions are bases on [[statefulness of protocols|stateless]] request/response pairs between a [[client]] and a [[server]]
- default [[port]] is TCP 80, but other ports can be used

### relationship of http versions to underlaying protocols
- versions 1.0 ro 2.0 are based on [[transmission control protocol (TCP)]] while HTTP/3 uses the [[user datagram protocol (UDP)]] based [[QUIC]]
#### HTTP/1.0
- one [[transmission control protocol (TCP)|TCP connection]] per request/response pair which is inefficient

#### HTTP/1.1
- possible to execute several requests using a [[transmission control protocol (TCP)|TCP connection]] with `keep-alive` option
- added pipelining: multiple requests can be sent before an answer arrived as long the order of responses matched the order of requests but this created problems and was removed

#### HTTP/2
- multiple requests can be sent at the same time over independent streams over a single [[transmission control protocol (TCP)|tcp connections]] → eliminates the oout-of-orderproblem of HTTP/1.1
- added push option to update when new data is avalibale

#### HTTP/3
- uses [[QUIC]] which is on top of [[user datagram protocol (UDP)]] instead of [[transmission control protocol (TCP)]]
- optimized for mobile applications because when the mobile network is swiched the [[transmission control protocol (TCP)|TCP connection]] has to be reestablished
- with [[QUIC]] the stream session can be reused

#### TCP connection
- [[transmission control protocol (TCP)|TCP]] connection is defined by two service endpoints ([[internet protocol (IP)|IP adress]], [[port]]) 
	→ a TCP connection is identified by a 4-tuple (server ip, server port, client ip, client port)
- a [[li socket|TCP socket]] is a connection endpoint instance with an [[internet protocol (IP)|IP adress]] and a [[port]] (but not uniquely identified by them)
- a network service (address/port) can have multiple sockets but only one of them is [[li listen|listening]] to incomming connections requests
- appart from the [[li listen|listening]] [[li socket]] there can be multiple [[li socket|sockts]] that are connected

Tags: code network
<!--ID: 1711969505153-->
END