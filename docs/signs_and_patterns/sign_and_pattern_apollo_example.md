# Apollo example of identifiying Saturn V using *sign* and *pattern*

As introduced in the [Apollo 11 Activity Lifecycle](../activity/activityEagle.md), there were a number of key components that made up the whole assembly; the Saturn V rocket assembly (called the Launch Vehicle), the Command and Service Modules, the Lunar Lander and the crew.  Each of these parts were referred to informally as done in the last sentence, but for official engineering and operational documentation they were each assigned unique identifiers (LM-5 was the fifth build of the Lunar Lander but the first to be sent to the moon with a human crew).  An authoritative source of these identifiers (or *designations* as NASA called them) for the Apollo-7 to -17 Missions is available [here](https://history.nasa.gov/SP-4029/Apollo_18-10_Designations.htm).  The Saturn V Launch Vehicle for Apollo-11 was given the identifier of ["SA-506"](https://history.nasa.gov/afj/ap12fj/pdf/a12_sa507-flightmanual.pdf).  "SA-506" could be used as a surrogate for the identity of the actual launch vehicle in the documents, announcements, nameplates and official records for this particular Launch Vehicle.

??? note "The value of having `recognizing_language_community`"
    A quick search for the string "SA-506" reveals that many other things have been given the `identifier` "SA-506", notably a [HiFi Integrated Amplifier](https://www.hifiengine.com/manual_library/pioneer/sa-506.shtml), an anti-scratch acrylic sheet product, an SSD to USB adapter, and more.  In an enterprise (large organisation or business) setting the number of names & identifiers used in a formal setting (plans, technical documents, databases, physical equipment tagging, labels, intranet- and web-sites, etc that can be shared within and between departments, suppliers, customers, partners, etc) can be significant.  Keeping track of them and their intended (often specified) use is complex for humans and is very difficult for machines without a model like HQDM.  This illustrates the value in being able to capture the community (instance of `recognizing_language_community`) that will recognise the identifier as intended.

We will start by fetching the *physical_object* that represents the Saturn V launch Vehicle from the Activity Model dataset.  It has no `data_EntityName` predicate because this implementation uses the `representation_by_sign` HQDM model pattern.  However, it does have a predicate `member_of_kind` that puts it in the HQDM `class` named "*Earth_to_lunar_rocket_assembly_kind_of_functional_object*".

??? info "Saturn V Launch Vehicle represented in data"
    --8<-- "saturnVObjectsOnlyNodeEdgeGraph.mermaid"
    The node in **bold** is the uuid for the physical item that we will see in the subsequent diagrams is represented by the `identifier` that has the `pattern` "SA-506".  Its spatio-temporal extent is visible by it having both `beginning` and `ending` events and it having a `part_of_possible_world` predicate.

In order to have the *pattern* "SA-506" recorded we have an instance of `pattern` with the `data_EntityName` predicate set to the Literal "SA-506"(1).  An *identifier* is then created that `consists_of_by_class` that particular `pattern`.  The `identifier` (a subtype of HQDM's `Class` Entity Type(2)) is also restricted in its interpretation to a `recognizing_language_community` (an *actual* community)(3) by the `consists_of_in_members` predicate.
{ .annotate }

1.  How to store examples of (or pointers to) the actual *signs*, or the *patterns* that they are `member_of_`, is an implementation choice.  We have chosen to store the referenced pattern as a string using the `data_EntityName` property of the instance of *type* `pattern` as a record of the actual *pattern*.

2. The use of an upper-case "C" for `Class` is due to the significant role that the word *class* has in programming languages and, in this case, the website's documentation builder scripts.

3. This shows that the utility of SETs (HQDM `Class` and all of its subtypes) in HQDM is also down to their (intended) purpose.

This is illustrated in the next graph:

??? info "`identifier` constructed that has `consists_of_by_class` the `pattern` "SA-506""
    The node in **bold** is the instance of `pattern` that is "SA-506".  The instance of `identifier` `consists_of_by_class` that `pattern`.  The other predicates are expanded upon below.
    --8<-- "saturnVIdentifierNodeEdgeGraph.mermaid"
    In this example the predicate `represented` is used to indicate what *thing* is represented by this `identifier`.  Whether that is a good idea is down to the requirements around its use and subsequently is an implementation choice (see the [options](sign_options_by_diagram.md)).

We can now develop this example by adding a `representation_by_sign` *association* between an actual *sign* (an instance of `sign` that is a `member_of_` our `identifier` for this Saturn V Rocket Assembly), the `recognizing_language_community` that can recognise it for its intended purpose and the actual Saturn V Rocket Assembly itself:

??? info "`representation_by_sign` constructed such that a particular `sign` with the pattern "SA-506" is used to *identify* the actual Saturn V (rocket) launch vehicle"
    --8<-- "saturnVRepresentationBySignNodeEdgeGraph.mermaid"
    Although this example shows that the `sign` for the Saturn V Rocket Assembly and the rocket assembly itself share the same temporal bounds this does not need to be the case.  NASA will likely have designated "SA_506" before the rocket assembly was manufactured and certainly carried on using it to *represent* for decades after the rocket assembly was successfully used (and destroyed in that process).

We now have the necessary data objects to generate a "full" node-edge graph of the instances of both `representation_by_sign` and `representation_by_pattern` to specifically represent the Saturn V Rocket Assembly with the specified `identifier`:

??? info "Full `representation_by_sign` and `representation_by_pattern` Node-Edge graph"
    --8<-- "saturnVRBSAndIdentifierNodeEdgeGraph.mermaid"
    Well done if you have noticed that the two predicates `represents` and `represented` are present in this graph.  This can look like repetition (overkill).  This isn't the case for our worked example but for use of this implementation pattern in a business / enterprise application it will result in some data management choices.  This will likely result in only the `represents` relation being used where the `representation_by_sign` *association* is required and the `represented` relation being used where only `representation_by_pattern` is used.  Each involves a different trade-off.

As an illustration of data object re-use the following node-edge graph illustrates the same `recognizing_language_community` being used in multiple `representation_by_sign` and `representation_by_pattern` contexts:

??? info "Illustration of the participation of this particular `recognizing_language_community` in many `representation_by_sign` *associations* and `representation_by_pattern` relationships"
    --8<-- "saturnVRepresentationBySignAllParticipantRelsNodeEdgeGraph.mermaid"

Our final Apollo example is the node-edge graph of only the `identifier` (subtype of `representation_by_pattern`) to *represent* the actual Saturn V rocket assembly.

??? info "Illustration of the use of a particular `identifier` such that it directly `represented` the actual Saturn V rocket assembly"
    This example is just an extension of the first graph above that shows "`identifier` constructed that has `consists_of_by_class` the `pattern` "SA-506"".
    --8<-- "saturnVIdentifierAndPatternRepresentedNodeEdgeGraph.mermaid"

Although the use of *signs* &/or *patterns* to *represent* actual *things* is one of the more involved HQDM patterns it is in accord with how we used *signs* in our day-to-day lives.  These patterns (and the implementation choices relating to them) provide flexibility in modelling to accommodate any (and all?) uses of *signs* that can crop up in a business / enterprise context.

## References

HQDM book references: 13.9, 17.45

Entity Types: [`sign`](https://github.com/hqdmTop/hqdmFramework/wiki/sign), [`representation_by_sign`](https://github.com/hqdmTop/hqdmFramework/wiki/representation_by_sign), [`pattern`](https://github.com/hqdmTop/hqdmFramework/wiki/pattern), [`identification`](https://github.com/hqdmTop/hqdmFramework/wiki/identification), [`recognizing_language_community`](https://github.com/hqdmTop/hqdmFramework/wiki/recognizing_language_community)

MagmaCore (Java) reference: [`sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Sign.java), [`representation_by_sign`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/RepresentatioBySign.java), [`pattern`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Pattern.java), [`identification`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Identification.java), [`recognizing_language_community`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/RecognizingLanguageCommunity.java)

Source code for this example is available [here](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/sign/SignExample.java)