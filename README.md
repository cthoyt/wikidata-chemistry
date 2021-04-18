# wikidata-chemistry

Cache of Chemistry in Wikidata

```shell
curl -H "Accept: text/tab-separated-values" --data-urlencode query@wikidata/inchikeys.rq -G https://query.wikidata.org/bigdata/namespace/wdq/sparql -o tmp1.tsv
cat tmp1.tsv | sed -e "s/\"Q//" | sed -e "s/\"//g" | grep -v "wikidata" | sort -n | sed -e 's/^/Q/' | split -l 100000 -d - inchikeys_
```