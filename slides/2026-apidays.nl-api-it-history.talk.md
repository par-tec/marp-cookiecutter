---
marp: true
theme: partec
paginate: false
title: How Italy shaped its API Governance Strategy: a retrospective
duration: 20m
level: beginner
tags:
- api-governance
- public-sector
abstract: |-
    # How Italy shaped its API Governance Strategy: a retrospective

    This talk explores the history of the Italian API strategy:
    how it was launched, what worked well, and the challenges faced along the way.

    Starting with a strong political mandate in 2018,
    Italy moved away from a framework based on SOAP and infrastructural gateways.
    This new strategy relied on REST technical guidelines built on Internet Standards,
    a national API Catalogue (api.gov.it),
    and a Schema Registry (schema.gov.it).

    We will cover the specific challenges of a public sector API strategy,
    the relations between central and local administrations,
    and the role of the EU.

    ## Key takeaways

    Finally, the session will share practical lessons learned in public sector digital transformation. Key topics include the necessity of top-down political commitment, the challenge of executing a unified strategy across a federated administrative structure, and the operational value of shifting cybersecurity and maintenance burdens away from local municipalities through centralized core services.

    ## Agenda

    - The Italian Government Digital Team: kickstarting the Country's Operating System under the Cabinet's Office. A strong politcal commitment under the guidance of Diego Piacentini, a former Amazon and Apple executive, appointed as the first Chief Technology Officer of the Italian Government in 2016.

    - API Governance was a priority, and was achieved in a long process

    Fase 1: 2018-2020. Technical Guidelines

    1. abolish the SOAP-only framework based on a mandatory gateway infrastructure, which become
    a bottleneck for implementers
    1. REST API mandate, with OAS3.0 and JSON for all new services
    1. Standardized API documentation and testing tools (api-oas-checker)

    Fase 2: 2020-2022. API Platform design

    1. Regulatory changes to implement api.gov.it, the national API catalogue and authentication platform.
    1. Next Generation EU funding and first implementations
    1. Agencies started to publish APIs and use the PDND, the Piattaforma Digitale Nazionale Dati, the National Digital Data Platform, for data sharing and interoperability.
    1. Design of schema.gov.it, the national schema registry, to standardize data models and ensure interoperability across services.

    Fase 3: 2022-2026. API Governance and National Platforms

    1. Rollout of api.gov.it
    1. Implemenation of schema.gov.it and tools to support the design of APIs compliant with the national standards.
    1. Tools for OAS validation according to the national guidelines.
    1. Further tools provided by the Digital Transformation Team to support the implementation of the API strategy, such as the API design tool and the API testing tool (e.g., MCP).

    ## Abstract

    ## TL;DR

    In 2016 Italy created the Digital Transformation Team, a group of experts tasked with kickstarting the country's digital transformation.
    The team was led by Diego Piacentini, a former Amazon and Apple executive, who reported directly to the Prime Minister of Italy.
    Core projects featured:

    - Digital Identity
    - API Governance
    - Platforms: National People's Registry
    - Cloud Strategy
    - Developer Community
    - IO App

    What worked well:

    - Strong political commitment and leadership
    - Technical expertise supporting the implementation of the strategy: a lot of good strategies fail in the execution
    - National platforms and registries for interoperability.

    What did not:

    - everything worked quite well wrt our track record :)
    - balancing the federal structure of the country with the need for a unified digital strategy,
    autonomy of implementing political choices does not necessarily mean autonomy of expenditure.
    Instead, providing central services to autonomies is a way to consolidate expenditure and
    relieving the burden of cybersecurity and maintenance from the shoulders of local administrations, which can then focus on delivering value to citizens.
---
<style>

section.cover .subtitle {
  font-size: 26px;
  color: rgba(0,0,0,0.6);
  margin-top: 16px;
}

section.cover .author {
  position: absolute;
  bottom: 60px;
  left: 540px;
  font-size: 28px;
  font-weight: 500;
}

</style>
---
<!-- _class: cover -->

<div class="title-area">

# How Italy shaped its API Governance Strategy


<div class="subtitle">2018-2022: a retrospective</div>

<div class="author">Roberto Polli <roberto.polli@par-tec.it></div>

</div>

---

## Who am I?

Roberto Polli @ioggstream

Solutions Architect @ par-tec.it

Python enthusiast, IETF HTTP & HTTPAPI workgroup

5 years in the Italian Government's Digital Transformation Team

Red Hat, MongoDB | MySQL Certified

---

## par-tec.it

- Software & Infrastructure system integrator
- Active in the open source scene for 20+ years
- A team of 200+ employees with 200+ professional certifications

---

## Agenda

My past experience in the Italian Government's Digital Transformation Team

- A strong political mandate: the Italian Government Digital Team
- Technology as an enabler
- API Guidelines and Standards: 2018-2020
- API Platforms Design (2020-2022) and rollout (2022-2026)
- Lessons learned and challenges ahead

:warning: Not affiliated nor endorsed by the Italian Government, all opinions are my own.

---

## A strong political mandate - 1

In 2016 Italy created the Digital Transformation Team, a group of experts tasked with kickstarting the country's digital transformation.

The team was led by Diego Piacentini, a former Amazon and Apple executive, who reported directly to the Prime Minister of Italy.

Identify core projects: National Digital Identity, API Catalog, National People's Registry, Cloud Strategy, Developer Community, IO App.

Hint: Italy is a federal country: 20 regions, 8k municipalities.

---

## A strong political mandate - 2

Make *public services
for citizens and businesses
accessible* in an easy manner,

via a mobile first approach,

with *reliable*, scalable and
fault tolerant *architectures*,

based on clearly defined *APIs*.

---

## Technology as an enabler 1

The Italian Interoperability Framework was based on SOAP and infrastructural gateways:

![alt text](image.png)

This limited the creation of new digital services:

- Expensive: needed a Gateway independently of the number of APIs;
- Inefficient: when communicating with non-governmental services and mobile.

---

## Technology as an enabler 2

To interact with non-governmental services and citizens' mobile applications,
REST APIs was a natural choice for the new strategy.

New standards supported this migration, and (e.g., RFC723x and OpenAPI 3.0) were adopted as the basis for the new API guidelines.

SOAP not forbidden, though.

---

## API Guidelines and Standards - 1

We started with:

- Stricted API Guidelines, leveraging HTTP features (idempotency, caching, status codes, ...)
- Scheme standardization based on industry standards
- Availability strategy

Challenges:

- Agencies had invested in SOAP and were not happy to migrate
- API Guidelines approval process was slow, due to stakeholder interactions.
- Agencies postponed the implementation of new services, waiting for the guidelines to be approved.

What worked:

- Find champions, focus on open services (e.g., less legal constraints), design tools;
- We had an internal team in charge of the IO App, the single mobile application for all public services, which demonstrated the value of REST APIs in practice.

---

## API Guidelines and Standards - 2

- Include API Marketplace in the guidelines
- Tools to support the design of APIs compliant with the guidelines (e.g., api-oas-checker)
- Move as much contract information out of PDFs and into machine readable formats (e.g., OpenAPI, JSON Schema) to improve consistency between documentation.
- API design training for public administrations (e.g., workshops)
- Identify gaps in the existing standards and propose extensions (e.g., HTTP, OAuth, OpenAPI)

Challenges:

- Interactions with standards bodies are slow;
- Agencies lacked funding for the transition;
- The API Catalogue was still a web page referencing a few APIs.

What worked:

- Knowledge dissemination;
- Improved organization knowledge of the standards bodies and processes;
- Shared tools and best practices with other countries, especially in the EU.

---

## API Platforms Design - 1

With Covid-19, it was better understood by
agencies and citizens that the ability to design and rollout digital services
was a key factor for the country's resilience.

At the core there was a regulatory change.

Originally, the legal basis for the National API Catalogue
were the API Guidelines, while data sharing exchanges should have been implemented
via the National Digital Data Platform (PDND) mandated by a specific law.

Since the data sharing plaform had a lot of legal and organizational challenges
due to the federal structure of the country,
it was then decided to converge the two initiatives into a single platform, api.gov.it
with a legal basis in the Digital Administration Code (CAD).

## API Platforms Design - 2

In the context of the Next Generation EU funding,
we consolidated the design of the two core API platforms:

- the API Catalogue and authentication platform (api.gov.it);
- the national schema registry (schema.gov.it), to standardize data models and ensure interoperability across services.

Challenges:

- Unified schemas across different agencies and services;
- Stimulate synergies between different providers;

What worked:

- Legal framework to support secure data exchanges and interoperability;
- Discoverability of APIs and data models;
- Agencies had funding and motivation to switch to REST;

---

## TL;DR

- Strong political commitment and leadership
- Technical expertise supporting the implementation of the strategy: a lot of good strategies fail in the execution
- National platforms and registries for interoperability.
- You don't always need laws,
- unless you do.
