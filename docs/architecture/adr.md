## The commitment is the information model which is represented by FRBR Work

## Different representat


Decision tree:

1. What is the identity of the product we commit to making? Practically speaking, what would the URI `/capaciteitskaart` identify?
2. Do varying representation techniques create different expressions or merely different manifestations?
3. Is the more expressive documentation a different resource or merely a different representation of the same resource than a schema?

My view:

1. The work we publish are versions of information models of data products.
2. These are agnostic with regards to representation techniques, i.e. if we were to move to -- say -- SHACL, this would not affect the identity of the work.
  a. The generated schemas -- e.g. Pydantic and JSON Schema -- are no less manifestations/representations of the work version, however their status might be different (informative rather than normative for example).
3. Various representations have differing levels of expression. Avro Schema is less expressive than SHACL, which is less expressive than natural language. However, all of these could viably be thought of as representations of the same resource, namely the work version.

---

So:

* `/capaciteitskaart` (work) is the information model of a data product
* `/capaciteitskaart/1.2` (work version) is the version of an information model of a data product, still agnostic with regards to representation technique
* LinkML/YAML and Antora/AsciiDoc are both manifestations of a work version with differing levels of expressiveness

Is a work version an information resource?

By choosing a manifestation, a work version becomes physically embodied and therefore represented in bits and bytes. This would imply it is an information resource, since all it takes is for it to be possible to do that _without losing the essence of the thing_.

However, some say that because of the differing expressiveness depending on the chosen representation technique, the essence of the thing might be lost. It would only becomes an information resource if a representation technique does not affect the expressiveness. For example, UML and LinkML variants of the same model would never be the same resource. In other words: each representation technique in fact yields a different resource, which has its own representations.

---

The information model is the identity, and it is 

















