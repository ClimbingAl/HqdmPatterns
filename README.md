# HqdmPatterns
## Documentation on implementation patterns for HQDM

A markdown-based documentation pack on implementation patterns for the use of the Topl Level Ontology (TLO)-based integration data model created by Dr Matthew West called ["HQDM"](https://www.oreilly.com/library/view/developing-high-quality/9780123751065/), using ```mkdocs material``` and related plugins.  The documentation is experimental and will be updated when capacity allows.

The goal of this documentation is to illustrate the data model patterns that are integral to HQDM and encourage consistent, practical implementation of them.  The code examples used will be released soon.  All the example files (TTL and mermaid files) have been generated in code using both [MagmaCore](https://github.com/ClimbingAl/MagmaCore) and the [Apollo Protocol Activity Editor](https://apollo-protocol.github.io/4d-activity-editor/).

The core patterns are introduced and worked examples have been created using the Apollo-11 Mission to the Lunar Surface.  The reasons for using the Apollo-11 Mission is that:

- It is well documented, with detailed engineering, operational and media made available by NASA.
- The Mission activities cover nearly everything that HQDM conceptually covers.
- Many people are familiar with the first trip by humans to the Moon, if not the details of the Mission.
- Using a modelling situation of something that actually happened is a good way to illustrate the decisions that have to be made to implement the information at appropriate quality.

While each example stands on its own, collectively they comprise an integrated set of data that illustrates what can be achieved with the use of a foundational data model that has a TLO at its roots.

Above all, the documentation is intended to encourage discussion.  Let me know if there are improvements that can be made.

I am grateful to the patience and insight into information quality management offered to me by Matthew West over the last 8 years.  Matthew passed away in early August 2023 but hopefully his work will become more widely recognised as paving the way to transformed information management within, and between, organisations that need it.

--------------------------------------------------------------

Some source material for the examples:

    https://www.nasa.gov/mission_pages/apollo/apollo11.html
    https://nssdc.gsfc.nasa.gov/nmc/spacecraft/display.action?id=1969-059C
    https://en.wikipedia.org/wiki/Lunar_Module_Eagle
    https://www.discovermagazine.com/technology/new-evidence-suggests-apollo-11s-lunar-ascent-module-could-still-be-orbiting
    https://history.nasa.gov/alsj/a11/a11.html
    https://www.dfj.com/ApolloConstruction/Apollo_11_LM-5_Construction_Log.pdf


# TODO:
- Add discussions to some pages.
- Example code release
- System & system-component
- Requirement methodology and Information Management Landscape pages
- All of the other remaining sections that have placeholder pages
- Lessons: degree of strictness, emergence, recognisably similar results, modelling decisions, etc
