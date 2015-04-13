## Improved Reasoning

### Faster, More Powerful, Easier Reasoning in Stardog 3.

Find out more about the new Stardog
[Simplified Reasoning](<http://docs.stardog.com/#_reasoning_levels>) and
[Equality Reasoning](<http://docs.stardog.com/#_same_as_reasoning>) support or
[Download Stardog 3](<http://stardog.com/#download>)
now.

Dear Friends of Stardog,

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
