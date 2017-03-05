# cy-es032017


# Elasticsearch
  - Home: https://www.elastic.co/
  - Download home: https://www.elastic.co/downloads/elasticsearch
  - Elasticsearch version: 2.4.4
    - tar_url: https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.4/elasticsearch-2.4.4.tar.gz

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
      - wget https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.4/elasticsearch-2.4.4.tar.gz

    - setup node
      - directory: `mkdir -p /opt/elasticsearch`
      - `cp ~ubuntu/elasticsearch-2.4.4.tar.gz  /opt/elasticsearch/`
      - extract tarball in `/opt/elasticsearch`
        ```
        tar xvzf elasticsearch-2.4.4.tar.gz
        ```
      - alternatives: https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html
      - setup user `useradd elastic`
      - setup permissions ` chown -Rvf elastic:elastic /opt/elasticsearch/`
      - open elasticsearch.yml `vim config/elasticsearch.yml'
        - change `network.host: 0.0.0.0`

      - increase max_map_count, run command: `sysctl -w vm.max_map_count=262144`

      - install plugins
        - hq: http://www.elastichq.org/, https://github.com/royrusso/elasticsearch-HQ
        - head: https://github.com/mobz/elasticsearch-head
        - kopf: https://github.com/lmenezes/elasticsearch-kopf

      - add node to cluster
        - data node:   `node.data = true`
        - client node: `node.client = true`
        - master node: `node.master = true`
        - 
        ```
          discovery.zen.ping.unicast.hosts: ["<node-1>","<node-2>", "<node-3>"]
          discovery.zen.ping.multicast.enabled:  false
        ```

  - Maintaining your cluster
    - Curator: https://github.com/elastic/curator

  - Install Kibana
    - version: 4.6.4
    - installer_url:
      - debian/ubuntu: https://download.elastic.co/kibana/kibana/kibana-4.6.4-amd64.deb
      - redhat/centos: https://download.elastic.co/kibana/kibana/kibana-4.6.4-x86_64.rpm
      - tar_url: https://download.elastic.co/kibana/kibana/kibana-4.6.4-linux-x86_64.tar.gz
      
