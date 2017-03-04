# cy-es032017


# Elasticsearch
  - Home: https://www.elastic.co/
  - Download home: https://www.elastic.co/downloads/elasticsearch
  - Elasticsearch version: 5.2.2
    - tar_url: https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.2.2.tar.gz

  - Cluster:
    - Node1: 24
      tags:
    - Node2: 105
      tags:

  - Install cluster
    - update cache: sudo apt-get update -y
    - install java8
      `ssh -v ubuntu@<ip> < scripts/install_java8.sh`
    - validate if java8 is installed??
        `ssh -v ubuntu@<ip> < 'javac -version'`
    - get installer tarball
      - wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.2.2.tar.gz

    - setup node
      - directory: `mkdir -p /opt/elasticsearch`
      - `cp ~ubuntu/elasticsearch-5.2.2.tar.gz  /opt/elasticsearch/`
      - extract tarball in `/opt/elasticsearch`
        ```
        tar xvzf elasticsearch-5.2.2.tar.gz
        ```
      - alternatives: https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html
      
