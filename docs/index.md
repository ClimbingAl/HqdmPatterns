# HQDM model patterns

Welcome to *HQDM Patterns*, documentation on the general model-patterns embedded in the [HQDM](https://www.oreilly.com/library/view/developing-high-quality/9780123751065/) Top Level Data Model.

Why document the 'patterns'?  Well, getting to grips with the theory and structure of the Top Level Data Model (aka. Integration Data Model) that is HQDM is only part of what it takes to make use of it.  In this documentation the model theory underpinning HQDM is taken as given.  We focus instead on the choices involved in implementing the model for some scenarios that are commonly found in information management.  Despite being common, the use of approaches to achieve consistent ways of representing and managing the resulting models is rare.

??? question "Do I need to have any background in data integration or the theory behind HQDM to use this documentation?"  
    No.  The goal is to avoid much of the theory (without discarding it) and focus on how the modelling can be applied.  Much of this is about getting this right is about doing good, objective analysis of the need for information.  Many of the patterns in HQDM are both intuitive and emerge naturally from the construction that the book HQDM covers.  Applying them repeatably and effectively can enable a clearer path to managing information and getting the quality of it right for the decisions that it is intended to support.

??? info "Intended audience"
    Anyone interested in implementing an integration data model for the first time or as a reference for those who have some experience and want to learn more and share experience (once discussion feature is enabled).

*Personal note:* I am grateful to the patience and insight into information quality management offered to me by Dr Matthew West, author of HQDM, over the last 8 years.  Matthew passed away in early August 2023 but hopefully his work will become more widely recognised as paving the way to transformed information management within, and between, organisations that need it.

??? tip "Useful pre-reading"
    * Developing High Quality Data Models by Matthew West, Chapters 1 to 4 (the less theoretical ones &#128578)
    * Familiarity with the Information Management Landscape
        - What it takes to manage information in a way that is fit for purpose.  This covers everything that can be identified as necessary to ensure information is managed in a sufficiently mature manner. 
    * Use of the [Process-based Information Requirements Methodology](https://github.com/Apollo-Protocol/information-requirement-methodology)
        - See associated [Activity Modeller Tool](https://apollo-protocol.github.io/4d-activity-editor/)
    * Initial model mapping results

    Understanding the HQDM patterns can help in all of the activities listed above but they are essential to implementation activities, contributing to the consistent application of the model itself and allowing conscious decisions to be made around implementation choices and performance optimisations.

??? info "Format of each pattern"
    Each model pattern will include the following:

    1. Introduction, introducing the pattern and it's place in the HQDM model
    2. Type-instance pattern of data objects for each of the patterns
        - Includes example data that is integrated across all the abstract and Apollo-11 based worked examples
    3. Lightweight options - decisions that can be made to reduce the number of objects that need to be stored and the compromises involved.
    4. Validation and Query options
    5. Mapping options

The worked examples are based around a well-documented and familiar [real-world scenario](./scenario.md).