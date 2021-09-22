# InfluxDB Demonstration

This Repository contains a InfluxDB demonstration. It consists of:
* conda + spark dockerfile
* docker-compose for managing an InfluxDB, Chronograph Instance & JupyterHub based on the conda + spark Dockerfile

## Running the stack

To be able to run this stack, you need docker and docker-compose (> version 3).
To run everything, simply run from this position in your file system:

	docker-compose up

or

	docker-compose up -d

to run in background.

To stop the containers, run: 

	docker-compose stop

And to remove all states (empty database, remove all configs, ..) run:

	docker-compose down

**This will remove everything except the notebooks**

## Accessing the servies:

* JupyterHub: http://localhost:8000
* Chronograph: http://localhost:8889

## Notes

* To make working easier and keep the Notebooks even without the containers, the folder "notebooks" is mounted inside the conda-pyspark container. You can simply put your notebooks there and they will appear in JupyterHub
* Even though chronograph comes with a preset connection to InfluxDB you need to renew it (remove old or edit) and set the InfluxDBv2 Auth args (org + token) - you can get those from the docker-compose.yml file



# **THIS IS NOT A SECURE SETUP, DON'T USE IN A SECURE ENVIRONMENT**
