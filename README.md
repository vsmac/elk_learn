# elk_learn

# What is ELK?
ELK generally refers to the ELK Stack, a collection of open-source software tools used for searching, analyzing, and visualizing log data in real-time. The stack consists of three main components

Elastic Search:A distributed search and analytics engine. It's used for indexing, searching, and analyzing large volumes of data quickly and in near real-time.

Logstash: A data processing pipeline tool that ingests data from various sources, transforms it, and sends it to Elasticsearch.

Kibana: A data visualization and exploration tool that works with Elasticsearch to visualize the indexed data in the form of graphs, dashboards, and reports.

# What is Filebeat?
Filebeat is a lightweight, open-source data shipper that belongs to the Elastic Stack (formerly known as the ELK Stack). It's used to collect, aggregate, and ship log files or data from various sources to a central location, such as Elasticsearch or Logstash, for further processing and analysis.

Processing - The processing in the ELK Stack (Elasticsearch, Logstash, and Kibana) along with Filebeat involves collecting, transforming, storing, and visualizing log data
   >Filebeat is responsible for reading log files or events from various sources (such as system logs, application logs, etc.).
   >Logstash is a data processing pipeline. It processes the log data received from Filebeat or other data sources.
   >Elasticsearch stores the log data and provides powerful search and analytics capabilities.
   >Kibana is the visualization and exploration tool in the ELK Stack.
   
# https://dytvr9ot2sszz.cloudfront.net/wp-content/uploads/2023/05/image-19.png 

# elk installation documentation

# Import the Elasticsearch PGP Key

wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg

# Installing from the APT repository

sudo apt-get install apt-transport-https -y

# Save the repository definition

echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list

# To install the Elasticsearch

sudo apt-get update && sudo apt-get install elasticsearch

# To start Elasticsearch with security enabled

export ELASTIC_PASSWORD="<your_password>"

# To configure Elasticsearch to start automatically when the system boots up

sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service

# Elasticsearch can be started 

sudo systemctl start elasticsearch.service

# Check that Elasticsearch is running

sudo curl --cacert /etc/elasticsearch/certs/http_ca.crt -u elastic:$ELASTIC_PASSWORD https://localhost:9200 

# Configuring Elasticsearch

sudo vim /etc/elasticsearch/elasticsearch.yml

# find the line that specifies network.host, uncomment it, and replace its value with localhost like this.

network.host: localhost

# find the line that specifies http.port, uncomment it like this.

http.port: 9200

#(sudo curl --cacert /etc/elasticsearch/certs/http_ca.crt -u elastic:$ELASTIC_PASSWORD https://localhost:9200) If this command doesn't work then run this commands

# reset password of elastic

/usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic

# Then take the new password and put it in the place of $elasticsearch.like this

sudo curl --cacert /etc/elasticsearch/certs/http_ca.crt -u elastic:<new password> https://localhost:9200

{output} :
{
  "name" : "vagrant",
  "cluster_name" : "elasticsearch",
  "cluster_uuid" : "OsRbZ1OZTEGNq1GIEV70CA",
  "version" : {
    "number" : "8.15.2",
    "build_flavor" : "default",
    "build_type" : "deb",
    "build_hash" : "98adf7bf6bb69b66ab95b761c9e5aadb0bb059a3",
    "build_date" : "2024-09-19T10:06:03.564235954Z",
    "build_snapshot" : false,
    "lucene_version" : "9.11.1",
    "minimum_wire_compatibility_version" : "7.17.0",
    "minimum_index_compatibility_version" : "7.0.0"
  },
  "tagline" : "You Know, for Search"
}
