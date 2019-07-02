# Abstract
While Rust provides, out of the box, many different data structures for
cross-thread synchronization and communication, the same is not true for their
cross-process counterparts. In this talk we present the results of the research
at Standard Cognition on cross-process channels in Rust, an effort headed by
myself and two others, contained in a (soon-to-be) open source crate we call
neobuffer. Apart from our reference implementation, in the form of an SPMC
channel backed by a ringbuffer, we also explore the necessary components and
future work related to cross-process communication in Rust, such as an


# Details

The talk presents the work of three people, as a project for the Systems Team
at Standard Cognition. The immediate application for neobuffer, for us is
dealing with passing large video streams across processes while allowing for
them to be mutiplexed.

The flow of the talk will be:

* Motivation
* Existing alternatives (and why they aren't sufficient)
* Design Goals
* Trait presentation
* Implementation presentation
* Discussion on challenges
* Results
* Future work

In the results section I hope to present a minimal working example of
cross-proc communication using neobuffer, as well as some of the shortcomings
of our approach, which we hope to address in future work.

The intended audience is medium to advanced Rust programmers, and in particular
those dealing with systems level software and Linux.

# Pitch

It's somewhat rare to see cross-process work being done in Rust, where the
focus is usually stronger on cross-thread workloads / communications. neobuffer
is a novel attempt at creating a cross-process channel in pure rust, while
retaining safety guarantees across process boundaries. Our work on neobuffer
culminates into a handful of reusable crates, and the possible addition of a
new trait to the standard library as well as, hopefully, the building blocks
for much richer libraries that facilitate process-level parallelism or
cooperation in pure Rust.

I'm the original author of neobuffer and the ideas that make it sound,
following many long discussion with member of the Rust compiler team on how to
achieve safety in the weird conditions of cross-process shared state, and
(unfortunately) the only of it's three final authors that can attend RustConf.
I've been using Rust since slightly before 1.0, and I'm responsible for
transitioning much of Standard Cognition's infrastructure code into Rust.

