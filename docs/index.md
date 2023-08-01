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

## Other items
* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
