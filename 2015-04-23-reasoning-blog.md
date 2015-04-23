One of the reasons most SPARQL query engines don't do reasoning is that it is
computationally-expensive and difficult to do. In Stardog, it is turned off by
default so that our users do not pay the performance penalties if they don't
need the features. Some kinds of "inference" can be performed by using the
SPARQL CONSTRUCT form to generate triples that are not explicitly stated in the
database. For example, you can add that an individual has an aunt if she has a
parent with a sibling who is female or married to a female. Knowing the latter
few facts can create the former statement. The constructed triples can be added
back to the database and then queried directly.

The problem with this approach is that truth maintenance is a tricky business.
If the aforementioned child had an aunt solely because her father's brother was
married, if the uncle gets divorced, she may no longer technically have one. At
this point, you would still have the fact that she has an aunt in the database.
While it is certainly possible to remove that fact, knowing that you can or
should is not usually obvious. If it is stored in the default graph, you may
lose track of whether it had been asserted explicitly or derived from a
constructed rule.

This is why query-based reasoning is so powerful. Inferred triples can be
generated at query time based on the state of the database. Should that change,
the inferred results would change, but database administrators don't have to
worry about segmenting or cleaning up inferred statements.

Stardog has always been positioned as the leading graph database for high
performance querying and unequaled reasoning capabilities. We are always trying
to find ways to improve performance, increase the capabilities, and lower the
effort for users to benefit from these features. In Stardog 3.0, we have done
all three. We'll focus on performance improvements in the future, but for now
we'd like to draw your attention to two important improvements in Stardog's
reasoning abilities.

The first improvement is that users no longer need to know which reasoning level
to engage for basic kinds of inference. Most people can benefit from the feature
without having to know the difference between QL, RL, EL, RDFS and SL. The
distinctions between these levels are important in certain circumstances, but
they won't be for large numbers of uses. To remove this confusion, it is now
possible to simply turn reasoning on by setting a flag to "true". Consult the
[docs](http://docs.stardog.com/#_reasoning_levels)above for specifics.

The other major new addition is full support for OWL 2 equality reasoning. One
way you can indicate that two URIs point to the same resource is to explicitly
connect them via the `owl:sameAs` property. This suggests that any facts about
the one resource are also true about the other. It sounds simple in practice,
but the complexity escalates quickly. `owl:sameAs` is also symmetric and
transitive. This means that the equality applies in both directions (as it
would) and that if A is `owl:sameAs` B and B is `owl:sameAs` C, then A is
`owl:sameAs` C. This is a tremendously useful tool for integrating data sets and
it is used widely in the Linked Data space. In other words, the Berlin mentioned
in DBPedia is the same as the Berlin mentioned in the GeoNames project.

Stardog hasn't supported equality inferencing to date because of the performance
impact; but in Stardog 3 that's been changed so that now it is practical to
use. We'll talk more about some of the other performance improvements in Stardog
3 next time.
