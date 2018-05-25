
{
"title": "Efficiently streaming large JSON objects in .NET Core MVC",
"description": "Looking at ways to stream large JSON objects using .NET Core MVC framework",
"created": "2018-04-22T20:15:36Z",
"tags": [".NET Core", "JSON objects streaming", ".NET Core MVC"],
"slug": "efficiently-streaming-large-json-objects-in-.net-core-mvc"
}

Recently I was working on a project that had some of its
RESTful endpoints return quite large JSON data sets. 
Such were the specified requirements and I had nothing to do but 
to implement the required functionality.

So what are the possible approaches that can help resolve this 
efficiently without placing unnecessary pressure on our webserver?

1. The easiest and most convenient approach of them all is to 
use ORM, say EF Core and return IEnumerable straight back from your 
action and ensure you do not call ToList() on it prematurely so that
your result set is not materialized beforehand and eats all your memory.
This approach might get complicated quickly if you need to transform your results and
use other sources of data.

2. The other more low level approach is to use Json.NET streams directly and write
those straight into Response body stream, thus reducing memory pressure
a bit more and having more finer grained control over your data
and skipping deserialization overhead by doing it ourselves.

Here's how:

First we will create StreamingJsonResult, it's our custom ActionResult
that will handle our data serialization and streaming 

