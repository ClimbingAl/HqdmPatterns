# Apollo example of identifiying Saturn V using *sign* and *pattern*

As introduced in the [Apollo 11 Activity Lifecycle](../activity/activityEagle.md), there were a number of key components that made up the whole assembly; the Saturn V rocket assembly (called the Launch Vehicle), the Command and Service Modules, the Lunar Lander and the crew.  Each of these parts were referred to informally as done in the last sentence, but for official engineering and operational documentation they were each assigned unique identifiers (LM-5 was the fifth build of the Lunar Lander but the first to be sent to the moon with a human crew).  An authoritative source of these identifiers (or *designations* as NASA called them) for the Apollo-7 to -17 Missions is available [here](https://history.nasa.gov/SP-4029/Apollo_18-10_Designations.htm).  The Saturn V Launch Vehicle for Apollo-11 was given the identifier of ["SA-506"](https://history.nasa.gov/afj/ap12fj/pdf/a12_sa507-flightmanual.pdf).  "SA-506" could be used as a surrogate for the identity of the actual launch vehicle in the documents, announcements, nameplates and official records for this particular Launch Vehicle.

??? note "The value of having `recognizing_language_community`"
    A quick search for the string "SA-506" reveals that many other things have been given the `identifier` "SA-506", notably a [HiFi Integrated Amplifier](https://www.hifiengine.com/manual_library/pioneer/sa-506.shtml), an anti-scratch acrylic sheet product, an SSD to USB adapter, and more.  This illustrates the value in being able to capture the community (instance of `recognizing_language_community`) that will recognise the identifier as intended.

We will start by fetching the *physical_object* that represents the Saturn V launch Vehicle from the Activity Model dataset.  It has no `data_EntityName` predicate because this implementation uses the `representation_by_sign` HQDM model pattern.  However, it does have a predicate `member_of_kind` that puts it in the HQDM `class` *Earth_to_lunar_rocket_assembly_kind_of_functional_object*.

??? info "Saturn V Launch Vehicle represented in data"
    --8<-- "saturnVObjectsOnlyNodeEdgeGraph.mermaid"
    The node in **bold** is the uuid for the physical item that we will see in the subsequent diagrams is represented by the `identifier` that has the `pattern` "SA-506".  Its spatio-temporal extent is visible by it having both `beginning` and `ending` events and it having a `part_of_possible_world` predicate.

In order to have the *pattern* "SA-506" recorded we have an instance of `pattern` with the `data_EntityName` predicate set to the Literal "SA-506".  An *identifier* is the created that has 

??? info "`identifier` constructed that has `consists_of_by_class` the `pattern` SA-506"
    --8<-- "saturnVIdentifierNodeEdgeGraph.mermaid"
    The node in **bold** is the instance of `pattern` that is "SA-506".  The instance of `identifier` `consists_of_by_class` that `pattern`.  The other predicates are expanded upon below.


--8<-- "saturnVRepresentationBySignNodeEdgeGraph.mermaid"

--8<-- "saturnVSignAndIdentifierNodeEdgeGraph.mermaid"

--8<-- "saturnVRBSAndIdentifierNodeEdgeGraph.mermaid"

--8<-- "saturnVRepresentationBySignAllParticipantRelsNodeEdgeGraph.mermaid"

--8<-- "saturnVIdentifierAndPatternRepresentedNodeEdgeGraph.mermaid"

## References

HQDM book references: 13.9, 17.45

Entity Types: [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign), [`representation_by_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/representation_by_sign), [`pattern`](https://github.com/hqdmTop/hqdmFramework/wiki/pattern), [`identification`](https://github.com/hqdmTop/hqdmFramework/wiki/identification), [`recognizing_language_community`](https://github.com/hqdmTop/hqdmFramework/wiki/recognizing_language_community)

MagmaCore (Java) reference: [`sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Sign.java), [`representation_by_sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/RepresentatioBySign.java), [`pattern`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Pattern.java), [`identification`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Identification.java), [`recognizing_language_community`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/RecognizingLanguageCommunity.java)

Source code for this example is available [here](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/sign/SignExample.java)