---
# These are optional elements. Feel free to remove any of them.
status: proposed
date: 2023-05-09
deciders: Ryan Heap
consulted: Caitlin O'Toole, Adam Love, Chet Potvin, Jeff Rondeau
informed: Sitecore Practice Team
---
# Separate Rendering and Editing Host Roles

## Context and Problem Statement

Sitecore's [XM Cloud documentation](https://doc.sitecore.com/xmc/en/developers/xm-cloud/editing-hosts-and-rendering-hosts.html) introduces the concept of separating the presentation layer into two separate and distinct roles.  In previous headless incantations, presentation was served by the Rendering Host role, which included the public-facing site and the Experience Editor / Horizon server-side rendering.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Security Requirements around Rendering Host environment
* Architectural Complexity
* DevOps Complexity
* Duplication of front-end code / environment variable configuration
* Hosting feature parity between Rendering host (i.e. Vercel) and Editing host
* Speed of development
* Quality of Editing Experience
* Ownership of Front-End Code
* Performance and Scalability

## Considered Options

* Single Rendering Host Role
* Separate Rendering & Editing Host Roles

## Decision Outcome

Chosen option: "{title of option 1}", because
{justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### Single Rendering Host Role

#### Pro

* :heavy_check_mark: Less complexity: rendering hosts are a challenging concept for traditional Sitecore developers.  One role is enough for most implementations.
* :heavy_check_mark: Editing experience will enjoy the same performance and scaling benefits as the users of the public site
* :heavy_check_mark: One code base for all UI code
* :heavy_check_mark: Leverage rendering host DevOps pipeline for editing experience release consistency
* :heavy_check_mark: Supported by XM Cloud Pages

#### Cons

* :x: Editing environment (Experience Editor / Pages) cannot support a non-public rendering host i.e. IP White-list
* :x: Editing experience will include all features available to the public that may not be relevant for the author (i.e. OneTrust and other GTM injected code, Personalization, login gates, etc.)
* :x: Front-end Team is responsible for editing experience features and bugs 

### Separate Rendering and Editing Host Roles

#### Pro

* :heavy_check_mark: Supports rendering host requirements for non-public, security-controlled environments.
* :heavy_check_mark: Creates a clear separation between the Customer and Author experience from a feature standpoint.
* :heavy_check_mark: Supported by XM Cloud Pages
* :grey_question: Opportunity for Sitecore team to contribute to author-specific features 

#### Cons

* :x: Adds Architectural Complexity
* :x: Potential need for separate DevOps pipelines for Rendering and Editing hosts
* :x: Potential for duplicated front-end code base or git submodule
* :x: Potential for Sitecore developers to contribute to author-specific features