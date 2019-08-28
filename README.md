## Programming as Collaboration: Nested Data Structures Introduction

Welcome to "Programming as Collaboration." We're going to learn to use the
programming skills we know to work with nested data structures (NDS). "Nested"
means "complex" because we're talking about structures (`Array`s, `Hash`es)
that contain _other_ structures (`Array`s, `Hash`es). A very simple "nested"
data structure is an "Array of Arrays`:

```ruby
array_of_arrays = [ # containing Array (of Array)
  [1, 3, 5], # "Nested" Array 1
  [2, 4, 6]  # "Nested" Array 2
]
```

> "The `Array` called `array_of_arrays` has two elements. One element is an
> `Array` containing 3 elements. Those elements are the first odd numbers greater
> than `0`. The other element in `array_of_arrays` contains 3 elements that are
> the first even numbers greater than 0."

Let's use this introduction to help us identify four reasons of why nested data
structures are important to understand.

## Nested Data Structures Are Easier for Humans to Understand

Look back up at the inset section of text. Is that _fun_ to read? Not really.
To be _precise_, it becomes very hard to follow. Or imagine someone wants to
communicate about agricultural output in South America. Or imagine someone
wants to talk about the different sales levels of seven of your employer's
products in China. Would a big paragraph be what **you** want to read?

For humans, the answer is universally "no." Daniel Kahnemann in his book
_Thinking Fast and Slow_ discusses this at length. The human animal doesn't
like to think methodically (like a computer). A paragraph like the inset one
one above, is excruciating for humans and we, do a bad job. We want to skip
sentences, we skip ahead, etc. We might have to take notes, or track the words
with a pencil to keep our focus.

However, the code sample, provided you understand `Array` literal syntax, is
easy to read. Our human brains love it. It uses space and pattern to
communicate both the content inside, but some implicit rules (_In this `Array`
there are `Array`s. It seems like most inner `Array`s have three elements._).

The best part of nested data structures is that that they enable human
communication much better than text. So, for that meeting about agricultural
output, we'd recommend you to use a _table_. For the product mix in China
presentation, we recommend a _pie chart_. This will help the human-to-human
communication.

## Nested Data Structures Are Usable by Computers

A computer can't work with a pie chart or a table. The closes approximation it
can work with is a nested data structure. So NDS make it _easier_ for humans to
understand complex data, but they're the _only_ way a computer can understand
complex data.

## Nested Data Structures Are Transformed to Produce Insight

Early (1940s-1980s) programmers pretty much had one job description:

> "Take a bunch of raw data and put out a re-organized version of it, or do a
> calculation from all of it."

In fact, the complex world of programming was often housed in a department
called "data processing."

Imagine you're back in that early era of "data processing." Let's now suppose
someone asks us to:

> Get the element in the `1` index for all the nessted data.

Thanks to the human-brain-friendly nested structure, we can look at the code
and pretty quickly come up with `[3, 4]`. Since we know what the result should
be thanks to "eyeballing it," coding this solution is simple as well:

```ruby
array_of_arrays = [ # containing Array (of Array)
  [1, 3, 5], # "Nested" Array 1
  [2, 4, 6]  # "Nested" Array 2
]

def find_firsts(src)
  result = []
  0.upto(src.count - 1) do |inner_count|
    result << src[inner_count][1]
  end
  result
end

find_firsts(array_of_arrays) #=> [3, 4]
```

OK, we admit, determining the second odd or even number greater than zero isn't
_that_ exciting. But what if each of these inner `Array`s represented three
estimates, sorted least-to-most on remodeling two different rooms of your
house?

Suddenly things are much more exciting:

```ruby
array_of_bid_arrays = [ # containing Array (of Array)
  [1000, 3000, 5000], # "Nested" Array 1
  [2000, 4000, 6000]  # "Nested" Array 2
]

def what_we_can_get_away_with(src)
  result = 0
  0.upto(src.count - 1) do |inner_count|
    result += src[inner_count][0]
  end
  result
end

def if_money_were_no_object(src)
  result = 0
  0.upto(src.count - 1) do |inner_count|
    result += src[inner_count][2]
  end
  result
end

low_high_totals = [
  what_we_can_get_away_with(array_of_bid_arrays),
  if_money_were_no_object(array_of_bid_arrays)
]

p low_high_totals #=> [3000, 11000]
```

Wow! A difference of $8,000! The ability to take a nested structure and
transform is to produce insight is how most programmers of yesterday and many
of today justify their salaries!

## Nested Data Are Provided By Others for Us to Use

As you learn more about software development, you'll want to get data from
other sources to produce insights. Typically companies make this information
available through an "API." For the time being think of an API as a URL which
your code can contact that returns....you guessed it...a nested data structure.

Obviously, the data at Amazon is not curated by Jeff Bezos for the benefit of
_my_ program. The latitude / longitude data of all the coffee shops near my
iPhone's current location are not curated for the benefit of my program by Tim
Cook. The information about my GitHub repositories is not curated by Nat
Friedman for the benefit of _my_ program. The returned NDS _might_ have the
data I need. But oftentimes, we need to transform this provided data in order
to get the insights we need.

## Conclusion

As we've seen in this lesson, nested data structures are a tool for
representing complex information in a way that humans can read and that
computers can process. Using simple tools like expressions, statements,
methods, `Array` manipulation commands, and `Hash` manipulation commands, we
can transform NDS that we create or get from somewhere else in a way to produce
insight in a way that creates real value.

We call this module "Programming as Collaboration." These data are too complex
to work with in the way we might say "I want a cookie." These are data like
"Given the last 10 years of rainfall in Peru, I want to examine the correlation
between rainfall there and quinoa prices in Los Angeles." As such, we're going
to _collaborate_ with the computer. We're going to come up programs that take
complex data and get it closer and closer to our answer....before finally
giving us our answer. Much of the work in this module is in the
_transformation_ in order to get the answer.

Like life, when you're old enough to see how complex it is, getting a simple
answer is rare and sometimes how to get a murky answer is hard enough.
Computers can help do the data processing, but ultimately it's up to us to make
the final call.

The remainder of this module will train up our skill in working with NDS with
the collaboration of a computer to produce insight.
