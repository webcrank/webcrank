Webcrank
========

Webcrank is an ambitious project to build a fast, reliable and
__correct__, HTTP toolkit.

Heavily inspired by the approach that Webmachine takes, this project
aims to fulfill a similar goal, to fit somewhere above bit and string
twiddling at a HTTP primitive level, but below colour-by-numbers (and
likely with broken HTTP semantics) web framework du jour.

Webcrank shall provide a suite of tools that enable plumbing of your
well architected software into the horrors of HTTP, importantly these
tools should make it easy to produce a well behaving HTTP application
that is easy to implement, test and debug.


Implementation
--------------

This is where things get slightly interesting. The plan is to build
both a Scala _and_ Haskell version in parallel. It would be nice, but
not necessary, if the implementations end up being pretty close, but
it should be possible to leverage testing, docs and other resources
across both implementations.

See:
 * <https://github.com/webcrank/webcrank.hs>
 * <https://github.com/webcrank/webcrank.scala>


Collaboration
-------------

Everyone who is interested should feel welcome to contribute, and we
would like as many people as possible to get involved. There are a
number of people who strongly believe we need a strong implementation
of this type of toolkit in a functional, typed language (or even two),
and it won't happen without a number of people working together.

At the moment, I am organising things myself, so ping me on twitter
([@markhibberd](https://twitter.com/markhibberd)), email
(<mark@hibberd.id.au>), or just create an issue on
[github](https://github.com/webcrank/webcrak/issues).


Development
-----------

The development approach and techniques that we use should set this
project apart from others. Over time this list should grow, it could
be filled with a bunch of personal grievances against code, but
instead it has been seeded with the two over arching goals, and two
technical considerations.

#### Goals

  1. Correctness
  2. Reliability

#### Technical considerations

  1. Types
  2. No reflection. Ever. (See goal 1)


Prior Art
---------

This is obviously a well explored space. As stated, significant insight has
been taken from Basho's Webmachine, but there are a few other attempts in
Scala and other typed languages worth mentioning (raise pull request if you
want to add something to the list, a complete list will be helpful).

  1.  [Basho's Webmachine](https://github.com/basho/webmachine)
  2. [Webmachine HTTP Diagram](https://raw.github.com/wiki/basho/webmachine/images/http-headers-status-v3.png)
  3. [Stackmob's Scalamachine](https://github.com/stackmob/scalamachine)
  4. [@purefn's webapparatus](https://github.com/purefn/purefn-webapparatus)

Issues with the above libraries (and other HTTP stacks in Scala and
Haskell), the desire for a particularly coherent development approach,
etc... have led to the drive for this clean room implementation. But
while this is a fresh start, it would be unwise to ignore other
implementations. Ideally, we will be able to share ideas and even code
as things progress and reach a level of maturity.


Inspiration
-----------

This is the result of hard questions, complaints and prodding after a
twitter conversation between @markhibberd @jedws @possiblywrong
@dibblego @neutralthoughts @gersei @purefn and possibly a few others
that spewed over onto #scalaz.


On HTTP, and worse is worse
---------------------------

When this originally came up, there was a side discussion echoed a few
times, that can be paraphrased as "HTTP is shit, who cares, why
bother" (This sounds harsher than it actually was, but it summarises
the point nicely), and I even agree to some extent with this
sentiment. But it ignores an important point that is missed too often
in technology discussions: it really is 'turtles all the way down',
and by turtles I obviously mean total rubbish.

Examining this, say we ignore HTTP; we have sockets - again total
rubbish as a programming model; files - derp; tcp - blurg; hardware -
arghhhh!!!; these are not technologies we should be happy about, but
here we are programming against them. And this is why we need tools
and techniques that let us deal with the unreliable, the horrible, the
nasty bug-enabling technology of our industry and turn it something
that we can reason about, and use reliably.

This is why this project should exist, for those times when the
intolerable technology you are dealing with happens to be HTTP.
