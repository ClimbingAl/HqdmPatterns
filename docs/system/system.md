## **system** Entity Type

A foundational description of an actual [`system`](https://github.com/hqdmTop/hqdmFramework/wiki/system) is an organised or connected group of [`physical_object`](https://github.com/hqdmTop/hqdmFramework/wiki/physical_object).  Such *physical objects* can be biological organisms, people, organisations and intentionally constructed functional items.  For this set of pages we shall focus on **functional systems**; those that are intentionally arranged to have an `intended_role` when they are involved in an activity such that they participate in a way that is consistent with their *intended role* (the `intended_role` is the kind (`role'`) that the *systems* in question are `member_of`)(1).
{ .annotate }

1.  There is a wrinkle in the HQDM documentation for [kind_of_functional_system](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_functional_system) and [kind_of_functional_system_component](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_functional_system_component).  They are both missing the corresponding relation `intended_role_by_class`.  This has been raised as an issue in MagmaCore [here](https://github.com/gchq/MagmaCore/discussions/88#discussioncomment-8189734).  However, this relation is used in the worked example as it is appropriate, and useful, in the use of this model pattern.

For this page we shall introduce a *functional system* as a distinct whole-life individual, paving the way for us to add a *functional system component* in the [next page](./system_component.md)

### Spacetime Diagram

The diagram below indicates that a whole-life `functional_system` exists between two points in time (in the graphs and TTL below you can see that we have used real date-times to allow the generation of this spacetime diagram from the data).  

![Actual System](../extras/source-images/AnActualSystem.svg)
*Diagram generated using prototype SVG diagram generator using HQDM objects as input TTL.*

### Implementation
Each instance of an `functional_system` will be a `member_of_kind` of some `kind_of_functional_system` (this SET membership pattern is inherited by all subtypes of `individual`).  A node-edge graph that illustrates "An_Actual_System" from the diagram above is shown below, with the data object `id` for the instance of `functional_system` itself being shown in bold.  

--8<-- "systemAndKindExampleNodeEdgeGraph.mermaid"

From the node-edge graph it can be seen that for this kind of (admittedly generic, for this example,) *system* there is a `has_component_by_class` relation.  This is an indication that *systems* of this *kind* comprise component(s) of a certain *kind*.  For *functional systems*, frequently the objects of information management activities, this is a natural consequence of *systems* being designed, constructed / assembled / arranged by humans in an intended way (often in large numbers, like consumer electronics or medical and military equipment).

There is also an `intended_role_by_class` relationship for the instance of `kind_of_functional_system`, showing that *systems* that are members of this *kind* are intended to have a role as a participant in `activity`.  While it is used as a stub for this worked example it allows integrated representation of *functional systems* and the *activities* that they are intended to be (and actually) involved in(1).  For illustrative purposes the instance of `functional_system` itself is also granted `intended_role` to match the `intended_role_by_class` commitment to the *kind* that this *system* is member_of.(2)
{ .annotate }

1. As always, only if required to meet an information need.
2. In [HQDM](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_functional_object) these relations are mandatory, in EXPRESS the notation is "SET [1:?] OF role".   This is a good illustration of the conceptual nature of HQDM.  These relations are always true.  That doesn't mean that they have to be used in an information management context, as it may require work beyond what is needed to satisfy the information requirement.  However, having them expressed in HQDM in this way allows those using it to make a conscious decision to, or not to, use these sorts of model features.  An implementation consequence may be in code-based or model validation rules, like [Magma Core's builders](https://github.com/gchq/MagmaCore/tree/main/hqdm-canonical/src/main/java/uk/gov/gchq/magmacore/hqdm/rdfbuilders), that can throw exceptions if mandatory relationships are not present.

??? info "TURTLE"
    This TURTLE also includes the `functional_system_component` objects that are part of this worked example and are discussed in [this](system_component.md) page.

    ``` title="Functional system objects example in TURTLE"
    --8<-- "systemAndComponentPattern.ttl"
    ```

??? question "Do whole-life systems exist?"
    As with the similar question about whole-life [`individual`](../individual/individual.md#implementation) we should not take for granted that whole-life systems are easy to use.  They are a pragmatic compromise (and not incompatible with the foundational theory, just a pragmatic restriction on how types and SETs are surfaced in the model itself).

    Functional systems are familiar to us; doors, computers, cars, ships, railways, energy grids, power plants, scissors, kettles, etc. However, what isn't familiar to us is thinking about all of them as systems and how they can be composed of component parts (in some *systems* these can be called "sub-systems"). Behind the scenes these component parts may also be *functional_systems* in their own right.  If this is the case in the 'real' world then we should be able to represent them as they are (see [system_component](system_component.md)).

    However, systems (and their component parts) can change state frequently, in many cases pseudo-independently of each other (consider the examples listed in the previous paragraph and what happens to them, and their parts, as they operate normally).  In addition, *systems* can be damaged & upgraded and some can even be reconfigured.  If that turns out to be important to the information management of an actual *system* or *systems* then we need to bear this in mind when coming up with information model to accommodate this.  The model patterns in HQDM can accommodate all of these circumstances, as long as there is clarity about the need for modelling it and an objective, rigorous implementation approach.

    This documentation is an introduction to addressing these model patterns.  The authors are unaware of any information-based system that can address these challenges so far, so there is potential to pilot these techniques in any application area that is limited by not being able to keep track of information relating to all, or part, of the state of *systems*.

??? tip "Strategies for implementation of the `functional_system` pattern"
    TBC.  Cover system design, system analysis and additive approach.

## References

HQDM book references: 14, 17.10, 17.17, 17.28

Entity Types: [`system`](https://github.com/hqdmTop/hqdmFramework/wiki/system), [`state_of_system`](https://github.com/hqdmTop/hqdmFramework/wiki/state_of_system), [`kind_of_system`](https://github.com/hqdmTop/hqdmFramework/wiki/kind_of_system)

MagmaCore (Java) reference: [`system`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/System.java), [`state_of_system`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/StateOfSystem.java), [`kind_of_system`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/model/KindOfSystem.java).

MagmaCore (Java) builder classes: [`SystemBuilder.java`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/rdfbuilders/SystemBuilder.java), [`StateOfSystemBuilder.java`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/StateOfSystemBuilder.java), [`KindOfSystemBuilder.java`](https://github.com/gchq/MagmaCore/blob/main/hqdm/src/main/java/uk/gov/gchq/magmacore/hqdm/rdfbuilders/KindOfSystemBuilder.java).

Source code used to generate the data for this `system` example, combined with its associated `system_component`, is available [here](https://github.com/ClimbingAl/code-for-hqdm-patterns/blob/main/patterns/src/main/java/patterns/hqdm/system/SystemAndComponentsExample.java).
