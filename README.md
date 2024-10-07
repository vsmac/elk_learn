
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

  # file:///home/kaushal/Downloads/1_cvArbhLwuBHx6ZHayXqtZg.
