Brazilian Portuguese Metaphone Plugin for Elasticsearch
========================================

This plugin integrates the Metaphone algorithm for Brazilian Portuguese into Elasticsearch.

## Installing

```sh
./elasticsearch-plugin install https://github.com/Rogercf/elasticsearch-analysis-metaphone_ptBR/releases/download/7.3.2/elasticsearch-analysis-metaphone_ptBR-7.3.2.zip
```

## Building from source

```bash
mvn clean package
./elasticsearch-plugin install file:target/releases/elasticsearch-analysis-metaphone_ptBR-7.3.2.zip
```

## Compatibility

|Metaphone ptBR Plugin|Elasticsearch|JDK
|---|---|---|
| 1.0.0|5.0.0|1.8+|
| 1.0.1|5.6.3|1.8+|
| 6.2.2|6.2.2|1.8+|
| 6.3.2|6.3.2|1.8+|
| 7.2.0|7.2.0|1.8+|
| 7.3.0|7.3.0|1.8+|
| 7.3.1|7.3.1|1.8+|
| 7.3.2|7.3.2|1.8+|
| 7.11.2|7.11.2|1.8+|

## Usage

This plugin includes the 'br_metaphone' token filter. 

Example usage:

```bash
curl -XPUT -H "Content-Type: application/json" http://localhost:9200/myIndex -d '
{
  "settings": {
    "analysis": {
      "analyzer": {
        "myAnalyzer": {
          "tokenizer":  "standard",
          "filter": [
            "br_metaphone"
          ]
        }
      }
    }
  }
}'
```
