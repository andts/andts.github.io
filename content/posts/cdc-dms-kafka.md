+++
title = "Building a Change Data Capture Pipeline with AWS and Kafka"
description = "This blog post provides a step-by-step guide on how to build and configure a change data capture pipeline that captures all changes in a database and writes them into an audit log table in a useful format. The post covers the architecture of the pipeline, services used, and tips on how to set up each component."
date = "2024-04-28"
updated = "2024-04-28"
+++

# Intro

In this post, I will try to write a detailed step-by-step guide on how to build and configure a change data capture
pipeline that captures all changes in a database and writes them into an audit log table in a useful format.  
{{ admonition(type="warning", title="WIP", text="Please note that this post is a work in progress, and some sections may
be incomplete or require further refinement. I will continue working on it until I feel it is done, and if it currently
doesn’t have the information you are looking for - be sure to come back later.") }}

# Use Case

The use case for this setup is obviously an auditing system that keeps track of all changes in a database. Where could
this be useful? One option is using it for security reasons, to track user activity. Another or for activity logging
with the
possibility of reviewing changes in some data entity. Probably, it could even be helpful for debugging purposes.

# Architecture

{{ admonition(type="info", title="Architecture", text="Note that this post is not just an exercise but comes from personal
working experience, so some architectural decisions were preconditions that couldn't be changed. There are many ways
such a pipeline could be implemented, but I will only be talking about what I had experience with.") }}  
The pipeline in this post is built in AWS using the following services:

- **Aurora** - a cloud **PostgreSQL**, the primary data source and destination
- **Database Migration Service, DMS** - a service that captures and outputs the changes in Aurora
- **Managed Streaming for Apache Kafka, MSK with MSK Connect** - a queue (or a stream-processing framework, if you will)
  used to process the stream of data changes. **Kafka Connect** (**MSK Connect** in AWS-land) is a service that will put the
  data into its final destination.
- **Kafka Streams App** - a minimal app that transforms events so they are easy to use later. It will be built using
  **Spring Boot** with **Spring Kafka** and run in an **Elastic Container Service (ECS)** cluster.

# The Guide

## Step 1: Set up Aurora

## Step 2: Set up MSK Cluster

## Step 3: Configure DMS Task

## Step 4: Create MSK Connector

## Step 5: Build a Kafka Streams App

## Step 6: Test the Pipeline

