# Working with Nested Data Structures

## Introduction

Welcome to "Programming as Collaboration." In this series of lessons, we're
going to collaborate with the computer to discover _insights_ buried in complex
nested data structures (NDS). Complex nested data structures are things like
`Arrays` of `Arrays` of `Arrays` or `Hashes` of `Arrays` of `Hashes`.

We italicized _insight_ because we want to emphasize something very important.
There's a difference between raw data and conclusions drawn from that data. When
processed correctly, data can teach us many things. The conclusions we extract
from data with programming are called _insights_.

Let's take a data-into-insight example form history.  In 1854, the physician
John Snow recorded data identifying which Londoners in and about Broad Street
had contracted cholera. He thus had an initial data set, something very close to
a nested data structure. Snow then tested multiple hypotheses against the data,
but the one that fit the data best was this: cholera was being spread via an
infected pump in the neighborhood. This event is called "In the
[1854 Broad Street Cholera][bsoutbreak]."

It marks the birth of epidemiology and, in truth, the discipline that would come
to be called "data science."

## NDS into Insight

In the study of the cholera outbreak, we can see Snow's method:

* Raw data
  * households with death by cholera
  * water source by households with death
  * water source by households without death
* Human Effort
  * "Is there a common water source for households suffering cholera death?"
  * "Do households that don't use the Broad Street water pump avoid cholera
    death?"
  * "Why do individuals who work at the nearby brewery seem immune to cholera?"
* _Insight_: **The Broad Street pump is spreading disease! And the brewery
  workers avoid it by drinking low-alcohol beer all day!**

The work ahead of us looks a lot like John Snow's method:

* Raw data in the form of an NDS
  * Provided from our databases, or
  * Provided by a third party
* Form hypotheses and write code to provide results from the NDS
* Discover _insights_

Transforming raw data, usually held in complex nested data structures, to
_insights_ is one of the most essential roles programmers fulfill in
businesses. These _insights_ help us decide where to (or not to) build a
warehouse, evaluate whether an investment is likely to be positive or negative,
build alternative major-league baseball staffing strategies ("[Moneyball][]"),
or even, in the case of the [1854 outbreak][bsoutbreak], _save lives_.

## The Road Ahead

Our efforts will be divided into two phases:

1. Learn to build and evaluate complex NDS' so that we can work with them
2. Identify a process for writing programs that process NDS' into insights

## Conclusion

Nested data structures are tools for representing complex information in a way
that humans can read and that computers can process. Reading them and
processing them allows us to create _insights_ that improve our lives.

The remainder of this module will train up our skill in working with NDS with
the collaboration of a computer to produce insight.

To start, we'll introduce some of the simplest nested data structures. These
structures tend to be nested together to build complex data structures, so it's
helpful to understand them in isolation. The four we'll be digging into in the
next several lessons are:

* `Array` of `Array`s (AoA)
* `Array` of `Hash`es (AoH)
* `Hash` of `Array`s (HoA)
* `Hash` of `Hash`es (HoH)

While you might have seen these nested data structures before, these lessons use
more technical and more precise language to describe them. Additionally, we
discuss them with focus on how we are going to process them. Based on our
historical data, Flatiron students have often encountered difficulty moving from
"I understand these structures" to "I know how to work with these structures."
Don't lose this opportunity to make sure you know how to turn your knowledge
into _insight_.

Let's get started!

[bsoutbreak]: https://en.wikipedia.org/wiki/1854_Broad_Street_cholera_outbreak
[Moneyball]: https://grantland.com/features/the-economics-moneyball/
