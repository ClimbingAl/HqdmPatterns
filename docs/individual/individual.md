## **individual** Entity Type

One of the first HQDM patterns that is key to many of the more involved patterns is that of 'whole-life' [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual).  


??? info "Types-Supertype Hierarchy"
    The Entity Type [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual) is a subtype of [`state`](https://github.com/hqdmTop/hqdmFramework/wiki/state).  An [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual) can be a `member_of` one or more [`kind_of_individual`](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_individual).  An instance of [`state`](https://github.com/hqdmTop/hqdmFramework/wiki/state) can be a `temporal_part_of` an instance of [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual), as long as the constructional constraints of parthood are adhered to.  Any particular [`state`](https://github.com/hqdmTop/hqdmFramework/wiki/state), including an instance of [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual), can be `member_of` one or more [`class_of_state`](https://github.com/hqdmTop/hqdmFramework/wiki/class_of_state).

    --8<-- "individualSupertypes.mermaid"

### Spacetime Diagram

![Individual X and State Of X](../extras/source-images/individualX.svg)

### Relations

--8<-- "individualAndPhyscialObjectRels.mermaid"

## Implementation

--8<-- "individualAndKindNodeEdgeGraph.mermaid"

--8<-- "individualExampleNodeEdgeGraph.mermaid"



??? info "TURTLE"
    ``` title="Individual objects example in TURTLE"
    --8<-- "individualPattern.ttl"
    ```

??? question "Do whole-life individuals exist?"
    While the existence of material things is a central to 4-dimensionalist (perdurant) theory, it is worth asking whether the whole-life (individual) states exist.  States can be temporal parts of other states but is there a distinct category of whole-life states that represent the entire extent of the existence of material objects?  A simple illustration of one of the challenges is the temporal bounds for a whole-life state.  When do you, I or anything else material start and end at definite points in time?  

    A pragmatic response to this question is fourfold:

    1. In the powerset of all states there are sets that correspond to the set of whole-life states.  HQDM recognises them as an entity type that is a subset of the powerset of sets of states.  There are some nuances to this but is beyond the scope of this documentation.  HQDM took a pragmatic stance to address this as a model design decision.

    2. Working out and implementing the `beginning` and `ending` of any state requires care.  It can often be easier to identify the start &/or end events of temporal parts (from whicch minimum temporal extents of the whole can be derived).  Working out what is appropriate is an implementation decision.

    3. Can we afford not to employ whole-life states?  It can be very diffcult to keep track of states if it isn't clear what they are part of.  The `individual` entity type provides a pragmatic mechanism to address this.  This is a modelling decision.

    4. Model implementation requries understanding the information requirement and the associated implementation choices.  If a particular requirement is better served by not using the Entity Type `individual` (and it's subtypes) then this can also be done using HQDM.  This should only be done if the consequences are understood.

??? tip "Strategies for implementation of the `individual` pattern"
    GGG

Other properties may be chosen, or added, for additional data management purposes (e.g. logical deletion or data record copying).  They are described in the HQDM References below and are provided in the [`PatternsUtils.java`](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/cb73d64e61fda53b48af49f2793d6761ba79cd2a/thing/thing/src/main/java/patterns/hqdm/PatternsUtils.java#L31).
