## HQDM model patterns

Welcome to HQDM Patterns, documentation on the general model-patterns embedded in the HQDM top level data model.

Why document the 'patterns'?  Well, getting to grips with the theory and structure of the Top Level Data Model that is HQDM is only part of what it takes to make use of it.  In this documentation the model theory underpinning HQDM is taken as given.  We focus instead on the implementation of the model.

## Pre-requisites

* Familiarity with the Information Management Landscape
    - What it takes to manage information in a way that is fit for purpose.  This covers everything that can be identified as necessary to ensure information is managed in a sufficiently mature manner. [IML Diagram](extras/IML-Roadmap-V0.5.html) **UPDATE DIAGRAM TO MIGRATE FROM PREVIOUS DBB AND LINK IN WITH THIS DOCUMENTATION**.
* Use of the [Process-based Information Requirements Methodology](https://github.com/Apollo-Protocol/information-requirement-methodology)
    - See associated [Activity Modeller Tool](https://apollo-protocol.github.io/4d-activity-editor/)
* Initial model mapping results

Understanding the HQDM patterns can help in all of the activities listed above but they are essential to implementation activities, contributing to the consistent application of the model itself and allowing conscious decisions to be made around implementation choises and performance optimisations.

## Format of each pattern

Each model pattern will include the following:

1. Introduction, introducing the pattern and it's place in the HQDM model
2. Type-instance pattern of data objects (FULL)
    - Includes example data
3. Lightweight options
4. Validation and Query options
5. Mapping options

## A scenario for use in the examples

It is generally a good rule to model real things while exploring data models.  The role of data models and that data based on them is to support real-world decisions.  Those decisions will be about real activities and the material participants involved in, and associated with, them.  Developing models without reference to real, representative examples is a recipe for not capturing what's required.

For this documentation, to enable you to relate to data modelling decisions, how to construct the models and implement them, we will use a well-known, particular activity - the [Apollo-11 mission to the moon](https://www.nasa.gov/mission_pages/apollo/missions/apollo11.html).  As it was the first successful crewed lunar landing and return to Earth it provides plenty opportunity to illustrate key HQDM model patterns that are easy to relate to. In particular, the Lunar Lander Module number 5 that carried the small crew to the surface of the moon, as shown in the NASA image below, will feature.

![Tranquility Base](extras/lunar_module_small.jpg)
_Credit: [NASA Tranquility Base image feature](https://www.nasa.gov/multimedia/imagegallery/image_feature_616.html)_
