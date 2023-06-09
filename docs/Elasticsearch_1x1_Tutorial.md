---
title: Elasticsearch 1x1 Tutorial
---

# Elasticsearch 1x1 Tutorial

Elasticsearch Tutorial

## Index

Erstellen:

`PUT twitter`

<https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-create-index.html>

Löschen

`DELETE twitter`

<https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-delete-index.html>

Lesen:

`GET twitter`

<https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-get-index.html>

Übersicht:

`GET _cat/indices`

## Mapping

Erstellen:

    PUT twitter/_mapping/_doc
    {
      "properties": {
        "email": {
          "type": "keyword"
        }
      }
    }

<https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-put-mapping.html>

Lesen:

`GET /twitter/_mapping/_doc`

<https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-get-mapping.html>

Nested:

<https://www.elastic.co/guide/en/elasticsearch/reference/current/nested.html>

Reverse nested:

<https://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-reverse-nested-aggregation.html>

Parent join:

<https://www.elastic.co/guide/en/elasticsearch/reference/current/parent-join.html>

## Document

Hinzufügen:

    PUT twitter/_doc/1
    {
        "user" : "kimchy",
        "post_date" : "2009-11-15T14:12:12",
        "message" : "trying out Elasticsearch"
    }

<https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-index_.html>

Mehrer Daten hinzufügen/verändern:
<https://www.elastic.co/guide/en/elasticsearch/reference/current/docs-bulk.html>

## Search

Suchen:

`GET /twitter/_search?q=user:kimchy`

<https://www.elastic.co/guide/en/elasticsearch/reference/current/search-search.html>
