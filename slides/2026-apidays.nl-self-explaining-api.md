---
title: Self-explaining APIs
subtitle: A machine-readable, semantic approach to schema design
duration: 46m
level: intermediate
---


## Abstract

To integrate APIs from different domains and data providers, data need to have a well-defined meaning: imagine combining healthcare APIs using different units for human temperature, or financial APIs using different currencies.

This talk presents a semantic interoperability strategy based on:

- API (OAS3.0) and Schema (RDF) catalogues;
- specifications to attach RDF metadata to OAS3.0 API definitions and JSON Schema data models;
- tools to support API design and validation according to Italy's national interoperability guidelines.

The presentation covers ongoing standardization efforts (e.g., the registration of the OpenAPI and YAML-LD media types), a rationale of the specifications, and a demo of the Schema Editor: a tool providing a user-friendly interface to design semantic APIs.



## Description

This talk will present strategies and python tools to create semantically interoperable REST APIs. After the problem statement, various solutions will be presented, including:

- contract-first api development with OpenAPI 3, ontologies and controlled vocabularies like the ones published by the European Union;
- the rdflib and pyld python libraries for processing json-ld and RDF files;
- the use of centralized catalogs such as schema.org.

Prerequisites:

- no prior knowledge of semantics and ontologies;
- practical experience with OpenAPI, json schema and data modeling and API design in general.


##

- an API catalogue describing APIs with OAS3.0;
- a schema registry with RDF ontologies and controlled vocabularies;
- a specification based on JSON-LD and JSON Schema to
attach semantic metadata to (existing) API definitions and data models.
