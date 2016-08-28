# section 3.1 (Disocvery)

## Imp
`
make a HEAD request on the target URL, to check for an HTTP Link header with a rel value of http://www.w3.org/ns/ldp#inbox
`

Use solid : inbox 

Remove this example

```
HEAD /profile HTTP/1.1
Host: user.example

HTTP/1.1 200 OK
Link: <https://user.example/inbox/>; rel="http://www.w3.org/ns/ldp#inbox"
                                        

Discovering an Inbox with a HEAD request.
`

Remove this example
```

```
{
  "@context": "https://www.w3.org/ns/ldp",
  "@id": "https://user.example/profile",
  "inbox": "https://user.example/inbox/"
}
```

Do not conflate a profile and a user.  Replace with

```
{
  "@context": "https://www.w3.org/ns/ldp",
  "@id": "https://example.org/user#me",
  "inbox": "https://example.org/storage/inbox/"
}
```


Discovering an Inbox with a GET request to retrieve HTML.

Should say RDFa


General : rather use Turtle than JSON LD


# 3.2 Sending

Remove this example

```
POST /inbox/ HTTP/1.1
Host: user.example
Content-Type: application/ld+json

{
  "@context": "https://www.w3.org/ns/activitystreams",
  "@id": "",
  "@type": "Announce",
  "actor": { "@id": "https://example.org/profile#alice" },
  "object": { "@id": "https://example.org/annotation-1" },
  "target": { "@id": "https://user.example/article#introduction" },
  "updated": "2016-06-23T15:03:01Z"
}
```

Activity Streams poor choice of example.

# 3.5.0

`The Content-Type header MAY include a profile URI [RFC6906].`

Dubious

Remove this example

```
{
  "@context": "https://www.w3.org/ns/activitystreams",
  "@id": "",
  "@type": "Announce",
  "actor": { "@id": "https://example.org/profile#alice" },
  "object": { "@id": "https://example.org/annotation-1" },
  "target": { "@id": "https://user.example/article#introduction" },
  "updated": "2016-06-23T15:03:01Z",
}
```

AS poor choice

```
ActivityStreams 2.0 Support

Receivers SHOULD treat the application/activity+json media type as equivalent to application/ld+json; profile="http://www.w3.org/ns/activitystreams".
```

Remove


# 3.7.0

```
ActivityStreams 2.0 Support

Receivers SHOULD treat the requests from consumers for application/activity+json as equivalent to application/ld+json; profile="http://www.w3.org/ns/activitystreams", but if doing so additionally MUST return JSON-LD in compacted form.
```

Remove


# 4.3.0

Remove AS

Semantic pingback id is missing and "" -- BUG


# 5.3

Replace SHOULD with MAY 

Remove items on localhost


# 5.5

Remove

# 6

Remove

Use solid websockets
