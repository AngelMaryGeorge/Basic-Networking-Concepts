# curl
As a DevOps engineer, you’re frequently going to have to transfer data, and that means you should know how to use curl. 
curl is an open-source data transfer tool that supports multiple Application-layer protocols. 
It’s most commonly used for sending HTTP requests, which are requests for access to a resource on a server. 
curl is freely available and may already be on your system. If it isn’t, you can easily install it.

The most basic way to use curl is to perform an HTTP GET request (remember from our table earlier in this article that this is a request for a resource (HTTP) that returns the entire entity in the response (GET).

The basic syntax is: .

``` curl http://example.com ```
This will send an HTTP GET request to the example.com host.

If you’re checking an exact response code and only want to see response headers, you can use curl -I. The syntax looks like this in our example:

``` curl -I http://example.com ```
By default, curl uses the HTTP GET method. If you wanted to use another method to return a certain type of response, you can use the -X flag in your curl command followed by the type of request that you want. For example,

``` curl -X POST http://example.com ```
sends a curl HTTP POST (not GET) request (submitting a change to an object—in this case, a change to http://example.com).

curl is the master of data transfer, and we can even download files/store a file’s response with curl by using the -o flag. Syntax for this may look something like this:

``` curl http://example.com/faile -o output.file. ```
