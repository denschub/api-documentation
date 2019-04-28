---
title: Contacts
see_also:
  - target: aspects
---

{% include toc.md %}

## Get list of contacts in an aspect

Required API scope: `contacts:read`

### Request

~~~
GET /api/v1/aspects/:aspect_id/contacts
~~~

### Response

~~~json
[
  {
    "guid": "f50ffc00b188013355e3705681972339",
    "diaspora_id": "alice@example.com",
    "name": "Alice Testing",
    "avatar": "http://example.com/uploads/images/thumb_medium_83abe5319ef830c2bd84.jpg"
  },
  {
    "guid": "cb7e4aa0b82f0133e40d406c8f31e210",
    "diaspora_id": "bob@example.com",
    "name": "Bob Testing",
    "avatar": "http://example.com/uploads/images/thumb_medium_a51bf501fe86c198c0b1.jpg"
  }
]
~~~

## Add a user to an aspect

Required API scope: `contacts:modify`

### Request

~~~
POST /api/v1/aspects/:aspect_id/contacts
~~~
~~~json
{
  "person": "cb7e4aa0b82f0133e40d406c8f31e210"
}
~~~

### Parameters

| Name   | Type | Description                                                      |
| ------ | ---- | ---------------------------------------------------------------- |
| person | GUID | The GUID of the person that should be added to the given aspect. |

### Response

~~~
Status: 204 No Content
~~~

## Remove a user from an aspect

Required API scope: `contacts:modify`

### Request

~~~
DELETE /api/v1/aspects/:aspect_id/contacts/:person_guid
~~~

### Response

~~~
Status: 204 No Content
~~~

[aspects]: {{ site.baseurl }}/routes/aspects.html
