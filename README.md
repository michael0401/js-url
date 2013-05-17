#js-url.js

js-url.js is a utility module which provide functions for operating with url. 
It can be used both in the [node.js](http://nodejs.org) and browser.

##Documentation

* [urlParse](#urlParse)
* [urlFormat](#urlFormat)
* [parseQuery](#parseQuery)
* [formatQuery](#formatQuery)

<a name="urlParse" />
### urlParse(url_string)

Convert an url string to an url object. The keys and values of this object is shown in the following example.

__Example:__

    urlStr1 = 'http://user:pass@host.com:8080/p/a/t/h?query=string&query2=string2#hash';
    var newReference = urlUtils.urlParse(urlStr1);
    
__Result:__

    newReference == {
    "href":"http://user:pass@host.com:8080/p/a/t/h?query=string&query2=string2#hash",
    "path":"/p/a/t/h?query=string&query2=string2",
    "hash":"#hash",
    "search":"?query=string&query2=string2",
    "protocol":"http:",
    "auth":"user:pass",
    "host":"host.com:8080",
    "hostname":"host.com",
    "port":"8080",
    "pathname":"/p/a/t/h",
    "query":"query=string&query2=string2"
    }

<a name="urlFormat" />
### urlFormat(url_object)

Convert an url object to an url string.

__Example:__

    var url_string = urlUtils.urlFormat(newReference)
    
__Result:__

    url_string == 'http://user:pass@host.com:8080/p/a/t/h?query=string&query2=string2#hash'
    url_string == newReference.href
    
<a name="parseQuery" />
### parseQuery(query_string)

Convert an query string to an query object.

__Example:__

    var query_object = urlUtils.parseQuery(reference.search)
    
__Result:__

    query_object == {
    "query":"string",
    "query2":"string2"
    }
    
<a name="formatQuery" />
### formatQuery(query_object)

Convert an query string to an query object.

__Example:__

    var query_string = urlUtils.parseQuery(query_object)
    
__Result:__

    query_object == "?query=string&query2=string2"
    query_string == newReference.search
    
    
    
