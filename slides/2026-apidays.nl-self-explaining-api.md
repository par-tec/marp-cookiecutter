---
title: Self-explaining APIs
subtitle: A machine-readable, semantic approach to schema design
marp: true
duration: 25m
time: 1340-1405
level: intermediate
abstract: |-

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

---

<!-- footer: <p>:warning: All opinions are my own. Not affiliated nor endorsed by the Italian Government</p> -->
<style>

.container {
    display: flex;
    flex-direction: row;
    gap: 2em;

}
.col {
    flex: 1;
}

</style>

---

<!--
_class: cover
-->

<div class="title-area">

# Self-explaining APIs


<div class="subtitle">A machine-readable, semantic approach to schema design</div>

APIDays
Amsterdam, June 9th 2026

<div class="author">Roberto Polli - roberto.polli@par-tec.it</div>

</div>

---

<!--
_class: two-col
_footer: ""
-->

<div class="columns">

<div>

## Who am I?

Roberto Polli @ioggstream

Solutions Architect @ par-tec.it

Python enthusiast, IETF HTTP & HTTPAPI workgroup

5 years in the Italian Government's Digital Transformation Team

Red Hat, MongoDB | MySQL Certified
</div>

<div>

</div>
</div>

---
<!--
_class: sv-content
_footer: ""
-->
## par-tec.it

- Software & Infrastructure system integrator
- Active in the open source scene for 20+ years
- A team of 200+ employees with 200+ professional certifications

---
<div class="container">

<div class="col">

## Agenda

A semantic approach to schema design
improves API interoperability and integration
across domains and data providers.
</div>


<div class="col">

- Understanding API message
- Controlled vocabularies
- Contract-first Schema Design
- Central catalog for semantic assets

Audience: API designers and developers familiar with OpenAPI, JSON Schema and JSON-LD.

</div>

</div>

<!--
2'

Hi everybody! I am Roberto Polli from Par-Tec,
and today I will present
how to design schemas that simplify API mash up and interoperability.

I will start explaining the concept of controlled vocabularies
and how to use them for creating interoperable REST APIs based on a
contract-first schema design.

Finally, we'll show a central data catalog for semantic interoperability
will support this approach.

This is not a rigorous approach to semantic web, and I will skip
a lot of the theoretical background.


-->
---

<div class="container">
<div class="col">

## Semantics, why should I care?

Semantics ensures that messages are understood.

</div>

<div class="col">

We can't mash-up APIs with different formats and meanings.

```yaml
name: Rosie Mark
```

```yaml
name: Mark
surname: Rosie
fullName: Mark Rosie
```

</div>
</div>

<!--
1'

Semantics is the study of meaning and ensures that a message is understood

Here I have two ambiguous API messages ...

We can't mash-up APIs with different formats and meanings.

---

In the public sector, it is even more complex since the meaning of a
term (eg. "family" ) depends on the specific regulations (eg. fiscal family,
registered family, ...).

-->
---

## Attaching semantics to APIs

JSON-LD solves this problem by attaching semantic metadata to JSON documents
based on vocabularies.

<div class="container">


<div class="col">

- define concepts and relationships in a specific domain (e.g., healthcare, finance);
- validated by designated authorities;
- formally described via web standards (e.g., JSON-LD, RDF).

</div>
<div class="col">

```yaml
# Fields-to-concepts mapping
"@context":
  "@vocab": "http://schema.org/"
  fullName: name
  name: givenName
  surname: familyName
# Data
fullName: Rosie Mark
name: Mark
surname: Rosie
```

</div>
</div>

<!--
Vocabularies contain collection of terms and:
define concepts and relationships in a specific domain (e.g. healthcare, finance, ...)
validated by a designated authority (not necessarily a public authority)
formally described using the text/turtle media type or its JSON counterpart: JSON-LD which is a W3C specification

Those formats are equivalent, and you can convert from turtle to json-ld and back
without losing relevant information.

Complex vocabularies are called ontologies,
while simple list of terms are called codelists.

JSON-LD allows attaching semantic metadata to JSON documents, based on vocabularies.
-->

---

## Attaching semantics to APIs

JSON-LD allows attaching semantics to API payloads via
a `@context` header field referencing a remote URL
containing the mapping

```http
POST /api/v1/persons HTTP/1.1
Content-Type: application/json
Link: <http://example.com/context.jsonld>;
  rel="http://www.w3.org/ns/json-ld#context";
  type="application/ld+json"

{
  "fullName": "Rosie Mark",
  "name": "Mark",
  "surname": "Rosie"
}
```

<!--
JSON-LD allows attaching semantics to API payloads via a @context header field referencing a remote URL containing the mapping between the fields in the payload and the concepts in the vocabulary.

While this seems an easy way of addressing the problem of attaching semantics to APIS,
it has various limitations:
- you need to process all Link headers to find the context,
- you need to dereference the remote context URL, with all the security and performance implications,
- there is no way to assess this information at design time, which is a problem for contract-first API design and validation
-->

---

## Contract-first API design with semantics

The REST API Linked Data Keywords is a specification to attach semantic metadata to OpenAPI 3.0 API definitions and JSON Schema data models.

- a single OAS document for Schema and Semantics;
- super easy for non-semantic experts;
- support for OAS 3.0/ JSON Schema Draft 4;
- tools provided by the Italian National Catalog for Semantic Interoperability (schema.gov.it).

---
