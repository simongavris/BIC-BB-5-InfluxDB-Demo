FROM continuumio/anaconda3
RUN conda update -n base -c defaults conda -y && conda install -c conda-forge pyspark -y

# INSTALL JAVA 8
RUN mkdir -p /usr/java/ && \
    cd /usr/java/ && \
    wget https://download.java.net/openjdk/jdk8u41/ri/openjdk-8u41-b04-linux-x64-14_jan_2020.tar.gz && \
    tar xf openjdk-8u41-b04-linux-x64-14_jan_2020.tar.gz && \
    rm openjdk-8u41-b04-linux-x64-14_jan_2020.tar.gz
#ln -s /usr/java/jdk-16.0.2/bin/java /bin/java

# INSTALL SPARK 3.2
RUN mkdir /usr/spark/ && \
    cd /usr/spark/ && \
    wget https://dlcdn.apache.org/spark/spark-3.1.2/spark-3.1.2-bin-hadoop3.2.tgz && \
    tar xzvf spark-3.1.2-bin-hadoop3.2.tgz && \
    rm spark-3.1.2-bin-hadoop3.2.tgz

# SET ENVS
ENV JAVA_HOME=/usr/java/java-se-8u41-ri
ENV SPARK_HOME=/usr/spark/spark-3.1.2-bin-hadoop3.2


RUN useradd -rm -d /home/student -s /bin/bash -g root -G sudo -u 1001 student
USER student
WORKDIR /home/student