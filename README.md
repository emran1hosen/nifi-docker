# Here is an example docker-compose.yml file for a 3-node NiFi cluster:


This file will create three NiFi services, nifi1, nifi2, and nifi3, each running a separate instance of NiFi. The image used for each service is apache/nifi:1.18.0, which is the official Apache NiFi 1.18.0 image from Docker Hub. The ports are being exposed as 8080, 8081, and 8082. Each service is also using a named volume, nifi1_data, nifi2_data, and nifi3_data for data storage.

* Set up environment variables for cluster discovery, which allows each NiFi node to find the other nodes in the cluster. In the example above, the environment variables NIFI_CLUSTER_IS_NODE=true and NIFI_CLUSTER_NODE_PROTOCOL_PORT=8082 are set for each service. These variables tell NiFi that the service is a cluster node and the port on which it will listen for cluster communication.

* Create and start the services with the following command:

docker-compose up -d

You should now be able to access the NiFi web interface by going to the IP or hostname of any of the nodes in your browser on port 8080, 8081