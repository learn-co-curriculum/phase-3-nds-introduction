## Programming as Collaboration: Nested Data Structures Introduction

Welcome to "Programming as Collaboration." We're going to learn to use the
programming skills we know to work with _nested data structures_ (NDS).

"Nested" means "complex" because we're talking about structures (`Array`s,
`Hash`es) that contain _other_ structures (`Array`s, `Hash`es). A very simple
"nested" data structure is an "`Array` of `Array`s:"

```ruby
array_of_arrays = [ # containing Array (of Array)
  [1, 3, 5], # "Nested" Array 1
  [2, 4, 6]  # "Nested" Array 2
]
```

If you're familiar with `Array` literals, then this probably merits only a
shrug of the shoulders. It's fair to ask: "So what?" Remember that one of 
the core activities of a programmer is to _model_ the world so that our programs
can work on those models and provide us humans _insights_: who is the best 
quarterback, which investment should we make, how many recipes use "flour" as
an ingredient? In order the build models to answer these questions, we're going
to need to model complex data sets ("Proctor and Gambles Inc.'s Soaps", "All World
Cup Cricketers Since 1900").

Ultimately nested data structures allow us to model complex data in a way that
humans understand **and** that computers can speedily process. In the rest of this
lesson, we're going to talk about some of the specifics around how NDS' fulfill
this goal.

## Nested Data Structures Are Easier for Humans to Understand

Can you describe the nested `Array` above in English?

Try it yourself before you try ours.

Tried it? OK, here's our attempt:

> "The `Array` called `array_of_arrays` has two elements. One element is an
> `Array` containing 3 elements. Those elements are the first odd numbers greater
> than `0`. The other element in `array_of_arrays` contains 3 elements that are
> the first even numbers greater than 0."

Is that _fun_ to read? Not really. Is it easy to think about? Imagine what the
paragraph to describe agricultural output of South America looks like.  Humans
long ago learned that reading paragraphs like this is not a real strength of
ours (Daniel Kahnemann in his book _Thinking Fast and Slow_ discusses this at
length.).

The human animal doesn't like to think methodically (like a computer). When we
encounter complex paragraphs we skip sentences, we skip ahead, etc.  We might
have to take notes, or track the words with a pencil to keep our focus.

Humans have learned that we can share information like this far better in a bar
chart, a line graph, or a pie chart. Economic outputs are perfect for _tables_.

Unfortunately, computers don't understand pie charts. But if we structure our
data in NDS', we can get something that's easier for humans to read **and**
that the computer can work with.

Provided you understand `Array` literal syntax, your brain loves seeing data in
this visually "rhythmic" way.  The NDS uses space and pattern to communicate _both_ the
content inside, as well as describe some  rules (_In this `Array` there are
`Array`s. It seems like most inner `Array`s have three elements._).

For clarity in thinking and communicating, working with NDS' is a vital skill.

## Nested Data Structures Are Usable by Computers

We said it before, but a computer can't work with a pie chart or a table. The
closes approximation it can work with is a nested data structure. So NDS make
it _easier_ for humans to understand complex data, but they're the _only_ way a
computer can understand complex data.

## Nested Data Structures Are Transformed to Produce Insight

Early (1940s-1980s) programmers pretty much had one job description:

> "Take a bunch of raw data and output a re-organized version of it, or do a
> calculation from all of it."

In fact, the complex world of programming was often housed in a department
called "data processing."

Imagine you're back in that early era of "data processing." Let's now suppose
someone asks us to:

> Get the element in the `1` index for all the nested data.

Thanks to the human-brain-friendly nested structure, we can look at the code
and pretty quickly come up with `[3, 4]`. Since we know what the result should
be thanks to "eyeballing it," coding this solution can be verified quickly:

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
house? Suddenly this _exact same_ algorithm is much more exciting:

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
p low_high_totals[1] - low_high_totals[1] #=> 8000
```

Wow! A difference of $8,000! The ability to take a nested structure and
transform is to produce insight is how many programmers justify their salaries!

## Nested Data Are Provided By Others for Us to Use

As you learn more about software development, you'll want to get data from
other sources to produce insights. Typically companies make this information
available through an "API." For the time being think of an API as a URL which
your code can contact that returns....you guessed it...a nested data structure.

Obviously, the data at Amazon is not curated by Jeff Bezos for the benefit of
_my_ program. The latitude / longitude data of all the coffee shops near my
iPhone's current location are not curated for the benefit of my program by Tim
Cook and Apple. The information about my GitHub repositories is not curated by
Nat Friedman for the benefit of _my_ program. The returned NDS _might_ have the
data I need. But oftentimes, we need to transform this provided data in order
to get the insights we need.

## Conclusion

As we've seen in this lesson, nested data structures are a tool for
representing complex information in a way that humans can read and that
computers can process. Using simple tools like expressions, statements,
methods, `Array` manipulation commands, and `Hash` manipulation commands, we
can transform NDS' that we create or get from somewhere else in a way to produce
insight in a way that creates real value.

The remainder of this module will train up our skill in working with NDS with
the collaboration of a computer to produce insight.
