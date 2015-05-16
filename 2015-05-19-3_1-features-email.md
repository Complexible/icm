## New Features in Stardog 3.1

### Named Graph Security, BOSH Command Line Tools

Find out more about the new Stardog 3.1 Features
[Named Graph Security](<Link to Named Graph Security Docs>) and
[BOSH Command Line Tools](<https://github.com/complexible/stardog-release>) support or
[Download Stardog 3](<http://stardog.com/#download>)
now.

Dear Friends of Stardog,

We are always trying to add valuable new features to Stardog. We are excited about two new features that will be introduced in the 3.1 release. We are adding support for [Named Graph](<http://en.wikipedia.org/wiki/Named_graph>) Security and [BOSH](<http://bosh.io>) [Command Line Tools](https://github.com/complexible/stardog-release). Together these features will give you a more granular approach to permission-based security and ease the burden of supporting clusters of deployed Stardog instances.

You have been able to specify which users have access to which Stardog databases for quite some time, but now you will be able to restrict access to specific Named Graphs. These are useful structures for segmenting RDF triples based on source, production time, etc. within a single database. SPARQL allows you to reference these graphs without commingling all of the statements together. Imagine a shared data set with user-specific metadata for capturing preferences or specialized knowledgebases for certain classes of users.

The new security model maintains backward-compatibility so that the fine-grained support doesn't apply unless you turn it on. But, once you do, you can limit who is able to read, query or mutate triples stored within Named Graphs.

The cool thing about the [Stardog cluster support](<http://docs.stardog.com/#_high_availability_cluster>) introduced in 3.0 is that it can run on several instances for increased read throughput. The downside of the Stardog cluster support is that it can run on several instances for increased read throughput. Maintaining all of those instances by hand can be a tedious and error-prone process.

BOSH makes it possible to have a reusable set of tools, configurations and dependencies deployed across clusters in the AWS or local Lite Developer versions. Our new tools, configuration files and documentation are available as open source [on GitHub](<https://github.com/complexible/stardog-release>). They will help you maintain the excellent parts of the high availability cluster while reducing the maintenance burden.

Give these new features a try and keep your eyes open for all of the exciting things that are coming next.