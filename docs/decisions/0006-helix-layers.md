---
# These are optional elements. Feel free to remove any of them.
status: proposed
date: 2023-05-16
deciders: Caitlin O'Toole, Adam Love, Chet Potvin 
consulted: Jeff Rondeau
informed: Sitecore Practice Team
---
# Helix Layering Pattern

## Context and Problem Statement

Helix is a common pattern within traditional Sitecore MVC implementations.  The primary goals are: reusability and maintainability across solutions.  With the separation of UI code from backend Sitecore code, this pattern offers less value.

Do we want to continue using Helix within the backend solution?

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

These items are taken from the Sitecore [knowledge center](https://www.sitecore.com/knowledge-center/blog/511/introducing-sitecore-helix-4380) around Helix

* Quality
* Speed to Market
* Long-term value
* Sitecore-supported methodology
* Conventional development practices
* Shareability & Reusability

## Considered Options

* Helix Pattern
* Traditional n-tier architecture

## Decision Outcome

Chosen option: "{title of option 1}", because
{justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### Helix Pattern

#### Pro

* :heavy_check_mark: Generally accepted pattern supported by Sitecore
* :heavy_check_mark: Common pattern practiced by Sitecore Partners
* :heavy_check_mark: Allows for the creation of reusable Feature modules that can span customer verticals
* :heavy_check_mark: Follows [Principles of Package Design](https://medium.com/@mglover/principles-of-package-design-19cdb18ea35d)

#### Cons

* :x: Requires developer education and discipline
* :x: Requires strict lead oversight to ensure compliance
* :x: Lots of opportunity for dependency leaks between layers
* :x: Not a generally accepted practice for front-end development

### Traditional n-Tier Application Architecture

#### Pro

* :heavy_check_mark: Simpler Visual Studio Solution structure (generally Presentation, Business and Data layers)
* :heavy_check_mark: Less concern about dependency and stability principles
* :heavy_check_mark: Less oversight
  
#### Cons

* :x: Limited Reusability within Starter Kit
* :x: Solutions lack a definitive pattern or organization
* :x: Quality of code can diminish quickly
