# Elastic Search

The following instructions outline getting started with Elastic Search in Docker, on Windows.

## Starting Elastic Search in Development Mode

1. docker pull docker.elastic.co/elasticsearch/elasticsearch:6.2.2
1. docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.2.2

[Reference](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)


## Indexing Documents from PowerShell

```powershell
$body = '{
  "field1" : "value1",
  "field2" : "2018/03/18"
}'
$headers = @{}
$headers.Add("Content-Type", "application/json")
Invoke-WebRequest -Uri http://localhost:9200/index1/type1 -Method Post -Body $body -Headers $headers
```

[Reference](https://www.elastic.co/guide/en/elasticsearch/guide/current/index-doc.html)


## Searching for Documents from PowerShell

```powershell
$result = Invoke-WebRequest -Uri http://localhost:9200/index1/type1/_search?q=field1:value -Method Get
($result.Content | ConvertFrom-Json).hits.hits._source
```

[Reference](https://www.elastic.co/guide/en/elasticsearch/guide/current/search-lite.html)


## References

* [Elasticsearch.NET](https://www.elastic.co/guide/en/elasticsearch/client/net-api/current/index.html)
