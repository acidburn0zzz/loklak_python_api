## Python Loklak API
--------------------------------------------

If you want to create an alternative twitter search portal, the only way would be to use the official twitter API to retrieve Tweets. But that interface needs an OAuth account and it makes your search portal completely dependent on Twitters goodwill. The alternative is, to scrape the tweets from the twitter html search result pages, but Twitter may still lock you out on your IP address. To circumvent this, you need many clients accessing twitter to scrape search results. This makes it neccessary to create a distributed peer-to-peer network of twitter scrapers which can all organize, store and index tweets. This solution was created with loklak.

#### What is Loklak ?
It is a server application which is able to collect messages from various sources, including twitter. The server contains a search index and a peer-to-peer index sharing interface.

--------------------------------------------

#### Why should I use this ?
If you like to be anonymous when searching things, want to archive tweets or messages about specific topics and if you are looking for a tool to create statistics about tweet topics, then you may consider loklak. With loklak you can do:
- collect and store a very, very large amount of tweets and similar messages
- create your own search engine for tweets
- omit authentication enforcment for API requests on the twitter plattform
- share tweets and tweet archives with other loklak users
- search anonymously on your own search portal
- create your own tweet search portal or statistical evaluations, i.e.:..
- use Kibana to analyze large amounts of tweets as source for statistical data.

--------------------------------------------

# Documentation of the API and Usage Examples

To use the loklak app, first an object of the loklak type needs to be created. Do the following to install the `pip` module and add it to your `requirements` for the application.

`pip install python-loklak-api`

Loklak once installed, can be used in the application as

`from loklak import Loklak`

To create a loklak object you can assign the `Loklak()` object to a variable.
`variable = Loklak()`

eg. `l = Loklak()`

### API Documentation

##### Status of the Loklak server
Using the object created above, `l.status()` returns a json of the status as follows

```json
{
  "index_sizes" : {
    "messages" : 48683271,
    "users" : 14948939,
    "queries" : 726,
    "accounts" : 53,
    "user" : 5072266,
    "followers" : 90,
    "following" : 72
  },
  "client_info" : {
    "RemoteHost" : "",
    "IsLocalhost" : "false",
    "Accept-Language" : "en-US,en;q=0.5",
    "Host" : "loklak.org",
    "Accept-Encoding" : "gzip, deflate",
    "X-Forwarded-For" : "",
    "X-Real-IP" : "",
    "Via" : "1.1 proxy14.nitw (squid/3.1.8)",
    "User-Agent" : "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:42.0) Gecko/20100101 Firefox/42.0",
    "Accept" : "text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8",
    "Connection" : "close",
    "Cache-Control" : "max-age=259200"
  }
}
```
