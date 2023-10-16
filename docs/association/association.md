## **association** Entity Type

Association: What one thing has to do with another (or others) for a period of time.


??? question "What information requirement does this meet?"
    It is common to require information about how material things are associated.  Examples include:

    - Who is the owner of a particular car just before it is sold?

    - What organisation employs the person who is due to turn up to maintain the equipment tomorrow?

    - What documents relate to the original design of the powerstation that is due for modernisation?

    - What buildings have had their cladding replaced as a result of being identified post Grenfell?

    - ...

    The `association` pattern can be crucial in addressing these sorts of questions, and an almost limitless number of others like them.

This `association` pattern is a very common one where two or more `individual` objects are involved in some association for a period of time (e.g. an employment association between an employer and an employee).  The [`association`](https://github.com/hqdmTop/hqdmFramework/wiki/association) Entity Type is a whole-life individual for the period of the association between the [`participant`](https://github.com/hqdmTop/hqdmFramework/wiki/participant) states that are involved in it (it `consists_of` its participants).  A useful way to think about associations is that they are a 'state of affairs' between two or more `individual` things, with HQDM providing a fully stateful way of representing all of the states.


??? info "Types-Supertype Hierarchy"
    The Entity Type [`association`](https://github.com/hqdmTop/hqdmFramework/wiki/association) is a subtype of [`individual`](https://github.com/hqdmTop/hqdmFramework/wiki/individual) and [`state_of_association`](https://github.com/hqdmTop/hqdmFramework/wiki/state_of_association).  An [`association`](https://github.com/hqdmTop/hqdmFramework/wiki/association) can be a `member_of_kind` one or more [`kind_of_association`](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_association).  An `association` `consists_of` two or more [`participant`](https://github.com/hqdmTop/hqdmFramework/wiki/participant) states, each of which will be a `member_of_kind` of one or more [`role`](https://github.com/hqdmTop/hqdmFramework/wiki/role).  The `association` and the `participant` states that it `consists_of` all share the same period of time (the same temporal extent).

    --8<-- "associationTypesSupertypes.mermaid"

## Spacetime Diagram
The following diagram illustrates the association of two states, each state being a `temporal_part_of` an `individual` X and Y respectively.  The constituent states in this `association` all share the same temporal bounds.  This examples will be implemented below to illustrate the general entity-relationship and data patterns resulting from it.

![An association between a state of X and a state of Y](../extras/source-images/associationXY.svg)

## Data Object Block Diagrams
The block diagram below illustrates the data objects comprising the generic association shown on the space-time diagram above.

![Data object block diagram of association between a state of X and a state of Y](../extras/source-images/associationXYDataObjects.svg)

??? info "Full data object block diagram"
    The diagram below shows additional data objects required to populate the generic association pattern in full.  This illustrates that there is only ever a need to represent any concrete state (or HQDM class) once - providing these data objects can be accessed and shared.

    ![Full association between a state of X and a state of Y](../extras/source-images/associationXYDataObjectsFull.svg)


## Implementation
The data objects shown in the diagram above have been implemented using MagmaCore in [`AssociationExample.java`](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/association/AssociationExample.java).  The filtered node-edge graphs below correspond to the data objects and their relationships with each other to implement the `association` pattern.  The `Example_association_between_X_and_Y` and the `participant` objects named `Example_participant_state_of_X` and `Example_participant_state_of_Y` are shown in the first node-edge graph.

--8<-- "genericAssociationAndParticipantsNodeEdgeGraph.mermaid"

??? info "Extended node-edge graph"
    An extended node-edge graph showing some of the additional dependencies is shown next.

    --8<-- "genericAssociationAndParticipantsFullNodeEdgeGraph.mermaid"

These examples of `association` also build on the [individual examples](../individual/individual.md) data object examples, showing how data can be added to existing data that has been consistently generated using HQDM (with MagmaCore, in this case).  The TURTLE dataset showing the data used to generate these node-edge graphs is shown in the tab below.

??? info "TURTLE"
    ``` title="Association objects example in TURTLE"
    --8<-- "associationGenericPattern.ttl"
    ```

??? tip "Strategies for implementation of the `association` pattern"
    While HQDM is parsimonious with its entities and relationships there are some implementation choices that may make implementation easier depending on the application, its architecture and data storage facilities.  Here are some suggestions:

    - Don't store the `beginning` and `ending` relationships for each `association` as they can be queried from the `participant` states that it `consists_of`.

    - If lots of a particular `association` sub-type need to be created and the set membership of each is the same, consider creating a subtype of `association` and map it to a storage schema that includes the `participant` states and their `role`s.  This would be a mapping that could be mapped back to a full HQDM schema if/when required.

    - Sometimes the `beginning` or `ending` of an association isn't completely known (for example, it may still be in-place and the possible ending may be in the future).  In this case only store the `beginning` or `ending` that is known (as long as one of them is known).


## References

HQDM book references: 11.8, 17.13, 17.15, 17.16

Entity Types: [`association`](https://github.com/hqdmTop/hqdmFramework/wiki/association), [`participant`](https://github.com/hqdmTop/hqdmFramework/wiki/participant)

MagmaCore (Java) reference: [`association`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Association.java), [`participant`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/Participant.java)

Source code for this example is available [here](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/association/AssociationExample.java)


