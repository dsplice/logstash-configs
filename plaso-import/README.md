# Plaso-Import

Created this config as I was having issues with psort's output to Elasticsearch.  

Steps:

1:  Create plaso storage file (log2timeline)

2:  Create JSON line file (psort.py -o json-line)

3:  Edit logstash-plaso-json.conf to suite your needs

4:  Place logstash-plaso-json.conf in /etc/logstash/conf.d

5:  Create index pattern within Kibana for plaso-*
